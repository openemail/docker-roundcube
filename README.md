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
  volumes:

```



