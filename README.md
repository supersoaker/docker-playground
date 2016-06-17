# docker-playground
For using this playground just execute:
```bash
git clone https://github.com/supersoaker/docker-playground.git /var/docker
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
