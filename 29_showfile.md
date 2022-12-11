# Codigo 29: showFile

## ¿Que hace?
Muestra el contenido de un archivo

### **Observaciones**
No hay ninguna observación

```bash
#!/bin/bash
width=72
for input
do
  echo $input
  lines="$(wc -l < $input | sed 's/ //g')"
  chars="$(wc -c < $input | sed 's/ //g')"
  owner="$(ls -ld $input | awk '{print $3}')"
  echo "-----------------------------------------------------------------"
  echo "File $input ($lines lines, $chars characters, owned by $owner):"
  echo "-----------------------------------------------------------------"
  while read line 
  do
    if [ ${#line} -gt $width ] ; then
      echo "$line" | fmt | sed -e '1s/^/  /' -e '2,$s/^/+ /'
    else
      echo "  $line"
    fi
  done < $input

  echo "-----------------------------------------------------------------"

done | ${PAGER:more}

exit 0
```

### **Resultados**

![](https://github.com/SPM-UPVictoria/test-git-itsHaydo/blob/main/capturas/capturas/29.png)
**[Anterior](https://github.com/SPM-UPVictoria/test-git-itsHaydo)**

