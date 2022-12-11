# Codigo 66: getdope

## ¿Que hace?
envia en un correo electronico una pagina web

### **Observaciones**
No funciona como deberia, ya que curl indica que el formato del URL esta equivocado.

```bash

#!/bin/bash
now="$(date +%y%m%d)"
start="http://www.straightdope.com/ "
to="poncho.pjm.5a@gmail.com"   

URL="$(curl -s "$start" | \ grep -A1 'teaser' | sed -n '2p' | \ cut -d\" -f2 | cut -d\" -f1)"

( cat << EOF
Subject: The Straight Dope for $(date "+%A, %d %B, %Y")
From: Cecil Adams <dont@reply.com>
Content-type: text/html
To: $to

EOF

curl "$URL") | /usr/sbin/sendmail -t

exit 0
```
**[Anterior](https://github.com/SPM-UPVictoria/test-git-itsHaydo)**
