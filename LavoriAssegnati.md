# Lavori assegnati

# Nicolò e Alessandro

Implementazione di un software in grado di leggere i dati provenienti dalla porta seriale e visualizzare tali dati 
su dei grafici. Il codice per la visualizzazione viene implementato in Python.

Il dato o i dati vengono inviati con una struttura di questo tipo:

- All'inizio del dato deve esserci il tag identificativo
- Il dato è specificato dopo i : 
- alla fine del dato &
- nessuno spazio inserito
	
		<tag identificativo>:<dato>&<tag identificativo2>:<dato2>&
	
Esempio:
L'ADC legge un valore di 3182 sul canale 1 e 2185 sul canale 2, allora il dato inviato sarà:

	T1:3182&T2:2185&
	
	oppure
	
	1:3182&2:2185&
	
Nota: 
1. Il tag identificativo può essere un numero, univoco per ogni sensore, oppure una stringa, sta a voi decidere 
la soluzione migliore.
2. (IMPORTANTE) ***Il microcontrollore STM32 invierà tutti i dati sotto forma di array di byte***
3. I dati vengno inviati sotto forma di ***numero intero*** dovranno poi essere convertiti in un secondo momento 
in temperatura, pressione, accelerazione ... con delle funzioni apposite costruite in un secondo momento.
Il tag identificativo serve appunto a far capire a che sensore si riferisce il dato per poi poterlo convertire 
correttamente.
	
Per poter fare dei test la funzione ***sprinft*** potrebbe esservi utile per costruire la stringa con i dati.
	
Oltre al software dovete occuparvi dello studio del modulo ***SX1278*** che implementa la comunicazione wireless. 
Il modulo si basa sul protocollo LoRa.
Per il suo utilizzo si possono usare delle librerie.
Ho trovato questo tutorial insieme a una libreria per l'uso https://github.com/SMotlaq/LoRa valutate se è buona oppure no.
I primi test potete farli su Arduino se volete, poi il codice dovrà essere implementato su STM32.


# Luca

Lettura e scrittura sulla PDR delle principali informazioni per poter utilizzare il GPS e il baromentro presenti nella PDR.
Sulla PDR dovranno essere riportate le informazioni principali come: schema elettrico, modalità di comunicazione con il modulo,
formato dei dati ricevuto ed estrazione delle informazioni.

Se poi avanzi tempo puoi cominciare a pensare al diagramma di flusso per una funzione che legge i dati dal baromentro 
e restituisce appunto la pressione e la temperatura.

I dati letti dovranno essere inseriti in un array di 2 elementi chiamato ***datiBar***.

- datiBar[0]=Pressione
- datiBar[1]=Temperatura

I coefficenti di calibrazione del barometro vengono messi in un array chiamato ***coeffBar***. 

  
