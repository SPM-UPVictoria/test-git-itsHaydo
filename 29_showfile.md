# Codigo 29: showFile

## ¿Que hace?
El primer codigo genera un documento.db que contiene la mayoria de documentos de tu computador. Despues con el segundo codigo, permite buscar los que tengan ciertos caracteres

### **Observaciones**
Tiene que ser ejecutado como root

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
**[Anterior](https://github.com/SPM-UPVictoria/test-git-itsHaydo)**

