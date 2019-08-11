# docker-roundcube

This container hosts the RoundCube web mail service for OpenEMAIL. It is based on the official [roundcube/roundcubemail
](https://hub.docker.com/r/roundcube/roundcubemail)

# docker-compose

Add the follwing codes to your **OpenEMAIL** `docker-compose.yml`  file to intergrate `Roundcube` web mail into your **OpenEMAIL** installation.
```
roundcube-openemail:
  image: openemail/roundcube:latest
  container_name: roundcube
  environment:
    - TZ=${TZ}
    - ROUNDCUBEMAIL_DB_TYPE=mysql
    - ROUNDCUBEMAIL_DB_HOST=mysql
    - ROUNDCUBEMAIL_DB_PORT=3306
    - ROUNDCUBEMAIL_DB_USER=${DBUSER}
    - ROUNDCUBEMAIL_DB_PASSWORD=${DBPASS}
    - ROUNDCUBEMAIL_DB_NAME=roundcube
  volumes:
     ./data/roundcube/config/:/var/roundcube/config/
  restart: always
  dns:
    - ${IPV4_NETWORK:-172.22.1}.254 
  networks:
    openemail-network:
      aliases:
        - roundcube
```



