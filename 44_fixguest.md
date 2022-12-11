# Codigo 44: fixguest

## ¿Que hace?
Detras de un usuario de paso limpia todo

### **Observaciones**
No logro convertime en usuario de paso y solo llegamos al primer 'if', pero si funciona
 
```bash

#!/bin/bash

#Este codigo no muestra nada si se ejecuta, solamente al salir elimina las cosas
#que hayamos hecho o cambios recientes en el equipo

iam=$(id -un)
myhome="$(grep "^${iam}:" /etc/passwd | cut -d: -f6)"

if [ "$iam" != "guest" ] ; then
  echo "Error: you really don't want to run fixguest on this account." >&2
  exit 1
fi

if [ ! -d $myhome/..template ] ; then
  echo "$0: no template directory found for rebuilding." >&2
  exit 1
fi

cd $myhome
rm -rf * $(find . -name ".[a-zA-Z0-9]*" -print)
cp -Rp ..template/* .
exit 0
```
**[Anterior](https://github.com/SPM-UPVictoria/test-git-itsHaydo)**
