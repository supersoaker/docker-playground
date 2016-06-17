#MediaWiki
from <https://www.mediawiki.org/>
###Usage
Context: /var/www/mediawiki
####Docker compose
1. Make sure "main-mysql" is running 
2. Execute media wikis docker compose
```bash
docker-compose up -d
```
3. Configure Media wiki on <http://localhost:8080/>
  - Database host = "main-mysql"
  - Database pass = "123456"
4. Download the LocalSettings.php and put it into the file volume
```bash
cat ~/Downloads/LocalSettings.php | sudo docker exec -i mediawiki-web sh -c 'cat > /var/www/html/LocalSettings.php'
```

####Docker only
1. Start mysql server
```bash
docker run --name mysql -e MYSQL_ROOT_PASSWORD=123456 -d mysql/mysql-server:latest
```
2. Start media wiki
```bash
docker run --name mediawiki --link mysql:mysql -p 8080:80 -v /var/docker/mediawiki/www:/var/www/html -d synctree/mediawiki
```
3. Configure Media wiki on <http://localhost:8080/>
  - datenbank host: "mysql"
  - datenbank pass: "123456"
4. Download the LocalSettings.php and put it into the file volume
```bash
cat /home/parallels/Downloads/LocalSettings.php | sudo docker exec -i mediawiki sh -c 'cat > /var/www/html/LocalSettings.php'
```

