# Codigo 64 : log-duckduckgo-search

## ¿Que hace?
Genera un pequeño buscador
### **Observaciones**
Funciona directamente

```bash

#!/bin/bash

logfile="/searchlog.txt"

if [ ! -f $logfile ] ; then
  touch $logfile
  chmod a+rw $logfile
fi

if [ -w $logfile ] ; then
  echo "$(date): $QUERY_STRING" | sed 's/q=//g;s/+/ /g' >> $logfile
fi

echo "Location: https://duckduckgo.com/html/?$QUERY_STRING"
echo ""

exit 0
```
### **Resultados**

![](https://github.com/SPM-UPVictoria/test-git-itsHaydo/blob/main/capturas/capturas/64.png)

**[Anterior](https://github.com/SPM-UPVictoria/test-git-itsHaydo)**
