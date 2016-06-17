# docker-playground
For using this playground just execute:
```bash
git clone https://github.com/supersoaker/docker-playground.git /var/docker
```
To start mediawiki just execute the following lines:
```bash
cd /var/docker
docker-compose -f mysql/docker-compose.yml up -d
docker-compose -f mediawiki/docker-compose.yml up -d
```

Normal server file structure:
```
- /var/docker
     - /mediawiki
          - /www                # file volume for media wiki
          - docker-compose.yml  # configuration file for docker-compose
     - /gitlab
          - /www                # file volume for gitlab
          - docker-compose.yml  # configuration file for docker-compose
```
