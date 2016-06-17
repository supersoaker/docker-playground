```bash
docker run --name some-mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -d mysql/mysql-server:latest
```
```bash
docker run --name some-mediawiki --link some-mysql:mysql -p 8080:80 -v /var/docker/mediawiki/www:/var/www/html -d synctree/mediawiki
```
- media wiki einrichten unter http://localhost:8080
- datenbank host: {{container name vom mysql}} also "some-mysql"
- datenbank pass: "my-secret-pw"
- die heruntergeladene LocalSettings in den Docker container packen: (ersten teil austauschen)
```bash
cat /home/parallels/Downloads/LocalSettings.php | sudo docker exec -i some-mediawiki sh -c 'cat > /var/www/html/LocalSettings.php'
```
um die mediawiki zu starten und zu stoppen einfach:
```bash
docker stop some-mediawiki && docker stop some-mysql
```
```bash
docker start some-mysql && docker start some-mediawiki
```
