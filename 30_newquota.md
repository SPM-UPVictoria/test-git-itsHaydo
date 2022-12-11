# Codigo 30: newQuota

## ¿Que hace?
El comando quota muestra nuevas flags

### **Observaciones**
Tiene que ser instalado el comando quota-tools

## Instalacion en Archlinux
```
sudo pacman -S quota-tools
```
## Code
```bash
#!/bin/bash
flags=""
realquota="$(which quota)"
while [ $# -gt 0 ]
do
  case $1
  in
    --help)  echo "Usage: $0 [--group --verbose --quiet -gvq]" >&2
                       exit 1 ;;
    --group )  flags="$flags -g";       shift ;;
    --verbose)  flags="$flags -v";   shift ;;
    --quiet)  flags="$flags -q";       shift ;;
    --)  shift;           break ;;
    *)  break;         
  esac
done
exec $realquota $flags "$@"
```
### **Resultados**

![](https://github.com/SPM-UPVictoria/test-git-itsHaydo/blob/main/capturas/capturas/30.png)
**[Anterior](https://github.com/SPM-UPVictoria/test-git-itsHaydo)**
