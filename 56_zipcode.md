# Codigo 56: ZIPCODE

## ¿Que hace?
El primer codigo genera un documento.db que contiene la mayoria de documentos de tu computador. Despues con el segundo codigo, permite buscar los que tengan ciertos caracteres

### **Observaciones**
Tiene que ser ejecutado como root

#!/bin/bash
baseURL="http://www.city-data.com/zips"

/bin/echo -n "ZIP code $1 is in "

curl -s -dump "$baseURL/$1.html" | \
   grep -i '<title>' | \
   cut -d\( -f2 | cut -d\) -f1

exit 0
