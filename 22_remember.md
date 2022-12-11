# Codigo 22: Remember

## ¿Que hace?
El primer codigo genera recordatorios en forma de lista. Despues con el segundo codigo, permite mostrar la lista o solo algunos

### **Observaciones**
Tiene que ser ejecutado como root

## Codigo 1 del script 22
```bash
#!/bin/bash
rememberfile="$HOME/.remember"

if [ $# -eq 0 ] ; then
  echo "Enter note, end with ^D: "
  cat - >> $rememberfile
else
  echo "$@" >> $rememberfile
fi

exit 0
```

## Codigo 2 del Script 22
```bash
#!/bin/bash

rememberfile="$HOME/.remember"

if [ ! -f $rememberfile ] ; then
  echo "$0: You don't seem to have a .remember file." >&2
  echo "To remedy this, please use 'remember' to add reminders" >&2
  exit 1
fi

if [ $# -eq 0 ] ; then
  more $rememberfile
else
  grep -i -- "$@" $rememberfile | ${PAGER:-more}
fi

exit 0
```
### **Resultados**

![](https://github.com/SPM-UPVictoria/test-git-itsHaydo/blob/main/capturas/capturas/22.png)

**[Anterior](https://github.com/SPM-UPVictoria/test-git-itsHaydo)**
