# ARYA

## Requisiti di Sitema Preliminari

### Main Board
La Main Board sarà basata sull'esperienza acquisita dal lavoro sull'elettronica della Test Stand.  
Le funzioni che dovranno essere ereditate saranno:
* Misura di pressione (3 Canali)
* Misura di temperatura (4 Canali) 
* Scrittura dei dati su scheda SD
* Controllo di elettrovalvole (Opzionale)

In aggiunta, da sviluppare ex novo: 
* Utilizzo di componenti SMD
* Integrazione di IMU
* Integrazione di GPS
* Integrazione di un altimetro
* Aggiunta di un canale per controllare il sistema di recupero

### BMS (Battery Management System)
Il BMS deve essere in grado di proteggere le batterie (18650 Li ion) e fornire i voltaggi richiesti dalla main board (3,3V-5V e 24V).
Il circuito quindi consisterà di due parti: 

* Protezione della batteria
  * Overcharge
  * Overdischarge
  * Overcurrent (Short Circuit)
  * Polarity inversion
  
* Conversione del voltaggio
  * 24V boost voltage converter
  * 5V boost converter or 3.3V [LDO](https://datasheet.lcsc.com/szlcsc/1811201117_Advanced-Monolithic-Systems-AMS-AMS1117-3-3_C6186.pdf)

* Batterie 18650 Li Ion
 * Configurazione 3S o 4S

Non è ancora chiaro se è conveniente aggiungere un [circuito di carica](https://www.piekarz.pl/pl/pdf.php?id=30089) delle batterie sulla board stessa. 
