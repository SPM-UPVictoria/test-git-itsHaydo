# Codigo 99: dayInPast

## ¿Que hace?
Indica un dia en una fecha especifica
### **Observaciones**
Funciono directamente

```bash
#!/bin/bash

if [ $# -ne 3 ] ; then
  echo "Usage: $(basename $0) mon day year" >&2
  echo "  with just numerical values (ex: 7 7 1776)" >&2
  exit 1
fi

date --version > /dev/null 2>&1 	
baddate="$?"				

if [ ! $baddate ] ; then
  date -d $1/$2/$3 +"That was a %A."
else

  if [ $2 -lt 10 ] ; then
    pattern=" $2[^0-9]"
  else
    pattern="$2[^0-9]"
  fi

  dayofweek="$(ncal $1 $3 | grep "$pattern" | cut -c1-2)"

  case $dayofweek in 
    do ) echo "That was a Sunday"; 	;;
    lu ) echo "That was a Monday"; 	;;
    ma ) echo "That was a Tuesday"; 	;;
    mi ) echo "That was a Wednesday"; 	;;
    ju ) echo "That was a Thursday"; 	;;
    vi ) echo "That was a Friday"; 	;;
    sa ) echo "That was a Saturday"; 	;;
  esac
fi
exit 0
```


**[Anterior](https://github.com/SPM-UPVictoria/test-git-itsHaydo)**
