# Codigo 22: tooLong

## ¿Que hace?
Remplaza el echo y funciona como input
### **Observaciones**
Ninguna
```bash

#!/bin/bash
echo "$*" | awk '{ printf "%s", $0 }'

```
**[Anterior](https://github.com/SPM-UPVictoria/test-git-itsHaydo)**

