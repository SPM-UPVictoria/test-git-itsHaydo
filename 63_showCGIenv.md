# Codigo 63: showCGIenv

## ¿Que hace?
Simple imprime codigo html
### **Observaciones**
Ninguna

```bash
#!/bin/bash

echo "Content-type: text/html"
echo ""

echo "<html><body bgcolor=\"white\"><h2>CGI Runtime Environment</h2>"
echo "<pre>"
env || printenv
echo "</pre>"
echo "<h3>Input stream is:</h3>"
echo "<pre>"
cat -
echo "(end of input stream)</pre></body></html>"

exit 0
```

### **Resultados**

![](https://github.com/SPM-UPVictoria/test-git-itsHaydo/blob/main/capturas/capturas/63.png)

**[Anterior](https://github.com/SPM-UPVictoria/test-git-itsHaydo)**
