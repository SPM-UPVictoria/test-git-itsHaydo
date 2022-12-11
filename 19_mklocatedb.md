# Codigo 19: MKLOCATEDB

## ¿Que hace?
El primer codigo genera un documento.db que contiene la mayoria de documentos de tu computador. Despues con el segundo codigo, permite buscar los que tengan ciertos caracteres

### **Observaciones**
Tiene que ser ejecutado como root

## Codigo 1 del Script 19

```bash
#!/bin/bash

#TENEMOS QUE EJECUTAR CON ROOT#

locatedb="/var/tmp/locate_19code.db"

if [ "$(whoami)" != "haydo" ] ; then
  echo "Must be root to run this command." >&2
  exit 1
fi

find / -print > $locatedb

exit 0
```

**[Anterior](https://github.com/SPM-UPVictoria/test-git-itsHaydo)**
