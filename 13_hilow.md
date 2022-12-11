# Codigo 13: Hillow

## Funcionalidad
Es un pequeño codigo que realiza un pequeño juego de adivinar un numero, diciendo si es mas grande o mas pequeño

### **Anotaciones**
Este codigo de abajo no es el original, el original esta equivocado y este que se presenta esta corregido

```bash
#!/bin/bash
biggest=100                   
guess=0                       
guesses=0                    
number=$(( $RANDOM % $biggest + 1 ))    
echo "Guess a number between 1 and $biggest"

while [ "$guess" -ne $number ] ; do
  /bin/echo -n "Guess? " ; read guess
  if [ "$guess" -lt $number ] ; then
    echo "... bigger!"
  elif [ "$guess" -gt $number ] ; then
    echo "... smaller!"
  fi
  guesses=$(( $guesses + 1 ))
done

echo "Right!! Guessed $number in $guesses guesses."

exit 0


```
**[Anterior](https://github.com/SPM-UPVictoria/test-git-itsHaydo)**
