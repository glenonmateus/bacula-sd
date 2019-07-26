# Bacula Storage Daemon

Bacula Storage Daemon container. This daemon runs will store the backups.

# Environment

No variable are required to run the container. All have a default value.

### BACULA_SDNAME

File Daemon Name (default **bacula**)

### BACULA_SDPASSWORD

Bacula File Daemon Password (default **password**)

### BACULA_DIRNAME

Bacula Director Name (default **bacula**)

### BACULA_MONNAME

Monitor Name (default **BACULA_DIRNAME-mon**)

### BACULA_MONSDPASSWORD

Monitor Password (default **BACULA_SDPASSWORD**)

### BACULA_DEBUG

Bacula File Daemon Debug Level (default **50**)

# Running

To run the container:

```
docker container run --name bacula-sd \
  -e BACULA_SDPASSWORD=password \
  --mount type=volume,src=bacula-sd,dst=/etc/bacula/ \  
  -p 9103:9103 \
  glenonmateus/bacula-sd
```

# Docker Compose

```
version: 3.7

services:

  bacula-sd:
    image: glenonmateus/bacula-sd:9.4.4
    volumes:
     - bacula-sd:/etc/bacula
    environment:
     - BACULA_SDPASSWORD=password
    networks:
     - bacula
    ports:
     - 9103:9103
    deploy:
     replicas: 1
     restart_policy:
       condition: on-failure

networks:
  bacula:

volumes:
  bacula-sd:
```
