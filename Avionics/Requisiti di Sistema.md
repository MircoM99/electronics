# ARYA

## Requisiti di Sitema Preliminari

### Main Board
La Main Board sarà basata sull'esperienza acquisita dal lavoro sull'elettronica della Test Stand.  
Le funzioni che dovranno essere ereditate saranno:
* Misura di pressione (6 Canali)
* Misura di temperatura (4 Canali) 
* Acqusizione dati IMU
* Acquisizione dati Barometro
* Scrittura dei dati su scheda SD
* Scrittura dei dati su EEPROM
* Controllo di elettrovalvole
* Controllo cariche espulsione paracadute


### BMS (Battery Management System)
Il BMS deve essere in grado di proteggere le batterie (18650 Li ion) e fornire i voltaggi richiesti dalla main board (3,3V-5V, 12V e 24V).
Il circuito quindi consisterà di due parti: 

* Protezione della batteria
  * Overcharge
  * Overdischarge
  * Overcurrent (Short Circuit)
  * Polarity inversion
  
* Conversione del voltaggio
  * 24V Boost voltage converter
  * 12V Boost voltage converter
  * 5V e 3.3V Linear voltage regulator

* Batterie 18650 Li Ion
 * Configurazione 3S o 4S

Non è ancora chiaro se è conveniente aggiungere un [circuito di carica](https://www.piekarz.pl/pl/pdf.php?id=30089) delle batterie sulla board stessa. 
