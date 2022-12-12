# Codigo 38: DiskSpace

## ¿Que hace?
Muestra el espacio total en GB del equipo en uso

### **Observaciones**
Se puede ejecutar directamente

```bash

#!/bin/bash
tempfile="/tmp/available.$$"

trap "rm -f $tempfile" EXIT

cat << 'EOF' > $tempfile
    { sum += $4 }
END { mb = sum / 1024
      gb = mb / 1024
      printf "%.0f MB (%.2fGB) of available disk space\n", mb, gb
    }
EOF

df -k | awk -f $tempfile
exit 0
```
### **Resultados**

![](https://github.com/SPM-UPVictoria/test-git-itsHaydo/blob/main/capturas/capturas/38.png)

**[Anterior](https://github.com/SPM-UPVictoria/test-git-itsHaydo)**
