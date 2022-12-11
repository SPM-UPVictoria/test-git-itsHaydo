# Codigo 45: setdate

## ¿Que hace?
Este codigo cambia la fecha del computador

### **Observaciones**
Agregamos el codigo 'Library'

## 'Library'
```bash
. `dirname "$(readlink -f "${BASH_SOURCE[0]}")"`/5_validint
. `dirname "$(readlink -f "${BASH_SOURCE[0]}")"`/6_validfloat
. `dirname "$(readlink -f "${BASH_SOURCE[0]}")"`/8_echon
```


## Code
```bash

#!/bin/bash

. /home/haydo/Escritorio/CodigosMantenimiento/library.sh

askvalue()
{
  echon "$1 [$2] : "
  read answer
  if [ ${answer:=$2} -gt $3 ] ; then
    echo "$0: $1 $answer is invalid"; exit 0
  elif [ "$(( $(echo $answer | wc -c) - 1 ))" -lt $4 ] ; then
    echo "$0: $1 $answer is too short: please specify $4 digits"; exit 0
  fi
  eval $1=$answer  
}

eval $(date "+nyear=%Y nmon=%m nday=%d nhr=%H nmin=%M")

askvalue year $nyear 3000 4
askvalue month $nmon 12 2
askvalue day $nday 31 2
askvalue hour $nhr 24 2
askvalue minute $nmin 59 2

squished="$month$day$hour$minute$year"
echo "Setting date to $squished. You might need to enter your sudo password:"
sudo date $squished

exit 0
```
**[Anterior](https://github.com/SPM-UPVictoria/test-git-itsHaydo)**
