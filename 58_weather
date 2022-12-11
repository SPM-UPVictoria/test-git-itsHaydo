# Codigo 58: weather

## ¿Que hace?
Nos mandara el clima dado un codigo postal dado

### **Observaciones**
Por algo que tiene la API, no mande lo que deberia de mandar, pero el codigo funciona en lo que tiene que hacer

```bash

#!/bin/bash
if [ $# -ne 1 ]; then
  echo "Usage: $0 <zipcode>"
  exit 1
fi

apikey="b0304b43b2e7cd23" 

weather=`curl -s \
    "https://api.wunderground.com/api/$apikey/conditions/q/$1.xml"`
state=`xmllint --xpath \
     //response/current_observation/display_location/full/text\(\) \
     <(echo $weather)`
zip=`xmllint --xpath \
     //response/current_observation/display_location/zip/text\(\) \
     <(echo $weather)`
current=`xmllint --xpath \
     //response/current_observation/temp_f/text\(\) \
     <(echo $weather)`
condition=`xmllint --xpath \
     //response/current_observation/weather/text\(\) \
     <(echo $weather)`

echo $state" ("$zip") : Current temp "$current"F and "$condition" outside." 
```
**[Anterior](https://github.com/SPM-UPVictoria/test-git-itsHaydo)**
