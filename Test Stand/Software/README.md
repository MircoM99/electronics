# SOFTWARE
In questa cartella è conenuto un progetto per STM32CubeIDE che contiene il software da usare durante la fase di test.

Per il momento il software implementa un piccolo sistema di acquisizione dati, ovvero l'ADC interno legge i valori di tensione
presenti ai suoi ingressi ad intervalli temporizzati, li invia in memoria tramite DMA e li invia alla porta seriale per poter
essere letti da Desktop.

## Struttura del codice
Il codice è stato sviluppato seguendo i seguenti punti:
1. Per prima cosa è stato impostato un TIMER interno che temporizzi l'acquisione dei dati. Ipotizzando di dover leggere
10 sensori tra pressione e temperatura e di voler fare una lettura per 5 volte al secondo, il timer deve generare un
interrupt ogni 200ms.
Si è deciso di utilizzare il Timer3 che ha un clock ad una frequenza di 100MHz.
Il valore di arrivo del conteggio CNT e il valore del prescaler PSC devono essere impostati nel seguente modo:
5=100e06/ ((PSC+1)*CNT)
E' buona norma avere il valore di CNT più alto possibile si è deciso dunque di impostare: CNT=50000 e PSC=399
Il Timer3 deve generare un interrupt è stato abilitato nella sezione NVIC e impostato Trigger event selection 
a ***Update Event***.

2. A questo punto è stato attivato l'ADC attivando 10 canali e aggiungendo la richiesta d'usa della DMA in modalità
***circular***

3. Nel codice sorgente, in main.c, è stato attivato il timer tramite l'istruzione:
	
	> HAL_TIM_PWM_Start_IT(&htim3,TIM_CHANNEL_1)
	
i dati letti dall'ADC vengono salvati nella variabile ***datiSensori*** e nella routine di interrupt	viene specificato
l'indirizzo di tale variabile nell'avviamento dell'ADC: 

	> HAL_ADC_Start_DMA(&hadc1,(uint32_t *)datiSensori,10)
	
