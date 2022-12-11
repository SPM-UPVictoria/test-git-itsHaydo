# Codigo 22: tooLong

## ¿Que hace?
Convierte las primeras 72 lineas de un archivo de texto para que puedan ser interpretadas

### **Observaciones**
El codigo no tiene ninguna observacion

```bash

#!/bin/bash

width=72

if [ ! -r "$1" ] ; then
  echo "Cannot read file $1" >&2
  echo "Usage: $0 filename" >&2; exit 1
fi

while read input
do
   if [ ${#input} -gt $width ] ; then
     echo "$input" | fmt 
   else
     echo "$input"
   fi
done < $1

exit 0
```

**[Anterior](https://github.com/SPM-UPVictoria/test-git-itsHaydo)**
