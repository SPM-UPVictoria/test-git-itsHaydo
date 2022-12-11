# Codigo 31: mysftp

## ¿Que hace?
Simplemente ahce el comando sftp sea mas versatil

### **Observaciones**
No tiene ninguna observacion

```bash
#!/bin/bash

/bin/echo -n "User account: "
read account

if [ -z $account ] ; then
  exit 0;       
fi

if [ -z "$1" ] ; then
  /bin/echo -n "Remote host: "
  read host
  if [ -z $host ] ; then
    exit 0
  fi
else
  host=$1
fi
exec sftp -C $account@$host
```

**[Anterior](https://github.com/SPM-UPVictoria/test-git-itsHaydo)**
