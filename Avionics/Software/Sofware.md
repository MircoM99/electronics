# SOFTWARE 
In questa cartella è contenuto il software che implementa tutte le funzioni necessarie per l'elettronica di bordo.

## Principali Funzioni da implementare
Le principali azioni che il software implementato sul microcontrollore deve essere in grado di svolgere sono:
* Gestione del sistema di aborto
* Controllo della missione
* Raccolta dati
* Invio dei dati alla ground station


### Gestione del sistema di aborto
Il sistema di aborto ha il compito di salvare il razzo e proteggere le persone circostanti da esplosioni, volo
incontrollato e pericoloso.
Deve saper prevenire qualsiasi incidente.
* Esplosione: Se vengono rilevate pressioni o temperature oltre il limite. Deve saper abortire.

* Volo Incontrollato: Se la traiettoria di volo non è stabile o il giroscopio rileva che il razzo sta volando
orizzontale o peggio sta puntando verso il basso

* Errori nel Controllo Missione: Se la missione non viene rispettata e qualcosa va storto

* Aborto imposto da Ground Station: Se viene premuto il bottone rosso di Aborto dalla Ground Station

L’aborto prevede il blocco istantaneo della combustione, l’apertura della valvola di aborto per lo svuotamento del serbatoio e l’apertura del paracadute (come descritta in controllo
missione) per far atterrare in sicurezza il razzo.

### Controllo della missione
Il controllo missione prevede:
* Accensione della PCB, inizio raccolta dati, inizio timer di volo, ecc..
* Bloccaggio della combustione al momento opportuno.
* Apertura del paracadute alla quota opportuna.
La combustione viene bloccata dall’elettrovalvola al tempo opportuno, che viene calcolato simulando la traiettoria di volo futura grazie ai dati acquisiti dal sensore IMU, in modo da arrivare alla quota imposta dalla
missione. 

Il meccanismo di apertura del paracadute viene azionato ad una certa altezza da terra. L’apertura
del drouge chute andrà effettuata all’apogeo, quando il razzo ha velocità più contenute e così non si rischia di
rompere la tela. Il drouge chute ha il compito di rallentare la discesa del razzo mantenendola a tra 23-46 m/s. Il
paracadute viene aperto successivamente ad altitudini inferiori ai 450m e deve rallentare a meno
di 9m/s per un atterraggio morbido.
Per ridurre la possibilità di errore nella misura dell’altitudine, in caso di errori dai sensori o per altri motivi,
vengono usati due sistemi di calcolo dell’altitudine: il primo utilizza il barometro/altimetro mentre il secondo usa
la traiettoria calcolata dai dati dell’IMU (accelerometro-giroscopio). Inoltre l’apertura dei paracaduti è assicurata
dal sistema secondario Eggtimer che può azionare il sistema di recovery autonomamente dal sistema elettronico
principale.


### Raccolta dati:
La raccolta dati prevede l’acquisizione dei dati da tutti i sensori disponibili e il loro salvataggio su una memoria.
I dati raccolti possono essere sia RAW, così come il sensore ce lì dà, sia elaborati dalla PCB stessa come nel
caso della traiettoria simulata per poi confrontarli a posteriori.
Oltre ai dati viene salvato anche il Log di ciò che fa la PCB: gli azionamenti effettuati, quando sono state aperte
le elettrovalvole e quando sono stati accesi gli igniter per l’apertura del paracadute, quando decide di fare un
aborto e perchè, quando esegue un’ azione dettata dal controllo di missione, quando fa l’aborto perchè riceve
il segnale dalla Ground Station, ecc..
Sia il log che i dati devono essere sincronizzati allo stesso tempo mediante un RTC (Real Time Clock) comune
a tutti i sensori e alla PCB

### Invio dei dati alla ground station
I dati raccolti saranno inviati alla ground station tramite un modulo LoRa dedicato in comunicazione con il microcontrollore.
