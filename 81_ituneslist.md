# Codigo 81: ituneslist

## ¿Que hace?
Convierte las primeras 72 lineas de un archivo de texto para que puedan ser interpretadas

### **Observaciones**
El codigo no tiene ninguna observacion

```bash

#!/bin/bash

itunehome="$HOME/Music/iTunes"
ituneconfig="$itunehome/iTunes Music Library.xml"

musiclib="/$(grep '>Music Folder<' "$ituneconfig" | cut -d/ -f5- | \
   cut -d\< -f1 | sed 's/%20/ /g')"

echo "Your library is at $musiclib"

if [ ! -d "$musiclib" ] ; then
  echo "$0: Confused: Music library $musiclib isn't a directory?" >&2
  exit 1
fi

exec find "$musiclib" -type d -mindepth 2 -maxdepth 2 \! -name '.*' -print |
   sed "s|$musiclib/||"
```
**[Anterior](https://github.com/SPM-UPVictoria/test-git-itsHaydo)**
