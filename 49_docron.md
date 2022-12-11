# Codigo 49: Docron

## ¿Que hace?
Busca en la carpeta Crontab para ver si tiene algo que hacer diario, semanal o mensual

### **Observaciones**
Tiene que ser ejecutado como root

```bash

#!/bin/bash

rootcron="/etc/crontab"   
if [ $# -ne 1 ] ; then
  echo "Usage: $0 [daily|weekly|monthly]" >&2
  exit 1
fi

if [ "$(id -u)" -ne 0 ] ; then
  echo "$0: Command must be run as 'root'" >&2
  exit 1
fi

job="$(awk "NF > 6 && /$1/ { for (i=7;i<=NF;i++) print \$i }" $rootcron)"

if [ -z "$job" ] ; then   
  echo "$0: Error: no $1 job found in $rootcron" >&2
  exit 1
fi

SHELL='which sh'          

eval $job       
```
**[Anterior](https://github.com/SPM-UPVictoria/test-git-itsHaydo)**
