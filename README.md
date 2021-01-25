# docker-from-zero-to-hero

- [x] **exec container**: 
  
  + docker run --name:nginx_puzzle -dit -p 5555:80 --restart unless-stopped nginx:latest 
  + docker run --name mysql_start -e MYSQL_DATABASE=helloworld -e MYSQL_USER=sa -e MYSQL_PASSWORD=123456 -e MYSQL_ALLOW_EMPTY_PASSWORD=yes -p 3306:3306 mysql:8

- [ ] mount volume

- [X] **inspect container ip**: docker inspect --format '{{ .NetworkSettings.IPAddress }}' nginx_puzzle

- [X] **docker compose**

```docker
version: '3.1'

services:

  db:
    image: mysql:latest
    #command: --default-authentication-plugin=mysql_native_password
    restart: unless-stopped
    environment:
      MYSQL_ROOT_PASSWORD: 12345aA@

  phpmyadmin:
    image: phpmyadmin:latest
    restart: unless-stopped
    ports:
      - 1234:80
```

- [ ] create new docker network with 3 components: 

  - [ ] mysql
  - [ ] reddit
  - [ ] rabitmq

- [ ] worker: api message from rabitmq -> write mysql, reddit
