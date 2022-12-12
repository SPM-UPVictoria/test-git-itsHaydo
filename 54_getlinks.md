# Codigo 54: getlinks

## ¿Que hace?
Obtiene los subenlaces de una pagina web dada

### **Observaciones**
Requiere estar conectado a internet

```bash

#!/bin/bash

if [ $# -eq 0 ] ; then
  echo "Usage: $0 [-d|-i|-x] url"  >&2
  echo "-d=domains only, -i=internal refs only, -x=external only" >&2
  exit 1
fi

if [ $# -gt 1 ] ; then
  case "$1" in
    -d) lastcmd="cut -d/ -f3 | sort | uniq"
        shift
        ;;
    -r) basedomain="http://$(echo $2 | cut -d/ -f3)/"
        lastcmd="grep \"^$basedomain\" | sed \"s|$basedomain||g\" | sort |\
	     uniq"
        shift
        ;;
    -a) basedomain="http://$(echo $2 | cut -d/ -f3)/"
        lastcmd="grep -v \"^$basedomain\" | sort | uniq"
        shift
        ;;
     *) echo "$0: unknown option specified: $1" >&2; exit 1
  esac
else
  lastcmd="sort | uniq"
fi

#El Lynx al ser un navegador que funciona completamente en modo texto y se utiliza a través 
#de la línea de comandos, este software puede ser una buena solución para sistemas basados ​​en 
#consola, o incluso en servidores en caso de que sea necesario consultar la Internet.

lynx -dump "$1" | \
sed -n '/^References$/,$p' | \
  grep -E '[[:digit:]]+\.' | \
  awk '{print $2}' | \
  cut -d\? -f1 | \
eval $lastcmd

exit 0
```
### **Resultados**

![](https://github.com/SPM-UPVictoria/test-git-itsHaydo/blob/main/capturas/capturas/54.png)

**[Anterior](https://github.com/SPM-UPVictoria/test-git-itsHaydo)**
