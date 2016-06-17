# docker-playground
### Usage
For using this playground just execute:
```bash
git clone https://github.com/supersoaker/docker-playground.git /var/docker
```
To execute the docker containers use
```bash
cd /var/docker
docker-compose -f mysql/docker-compose.yml up -d
docker-compose -f mediawiki/docker-compose.yml up -d
docker-compose -f phpmyadmin/docker-compose.yml up -d
```

###File structure:
```
- /var/docker
     - /mediawiki
          - /www                # file volume for media wiki
          - docker-compose.yml  # configuration file for docker-compose
     - /mysql
          - /data               # file volume for mysql data
          - docker-compose.yml  # configuration file for docker-compose
     - /phpmyadmin
          - docker-compose.yml  # configuration file for docker-compose
```
