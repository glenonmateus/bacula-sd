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

`docker container run --name bacula-sd -e BACULA_SDPASSWORD=password glenonmateus/bacula-sd`
