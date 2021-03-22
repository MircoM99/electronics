# Electronics

Questa repository contiene i file per la realizzazione dell'elettronica per quanto riguarda tutti gli aspetti del progetto.

# Struttura della repository

La repository è composta da due cartelle principali di struttura analoga:

- `Test Stand`
  - `\Hardware`
  - `\Software`
  - `\Documents`
  
- `Avionic` 
  - `\Hardware`
  - `\Software`
  - `\Documents`
  
## Hardware

La cartella Hardware contiene tutti i file di progetto dedicati alla realizzazione del PCB corrispondente. I file di progetto sono realizzati attraverso l'uso del software open source [kicad](https://kicad.org/). Dopo aver installato il software, aprire il file di progetto con estensione `.pro` che si trova nelle directory

- `Test Stand\Hardware\Test Stand PCB\Test Stand PCB.pro`
- `Avionic\Hardware\Avionic PCB\Avionic PCB.pro`

Nella directory di progetto sono contenute le librerie Symbols (`Breakout_Test_Stand_PCB.lib`) e Footprint(`Test Stand PCB Breakout.pretty`) utilizzate. 

## Software

La cartella Software contiene i file di progetto dedicati alla realizzazione del software che girerà sul sistema corrispondente. I file di progetto sono realizzati attraverso l'uso del software [Microsoft Visual Studio Code](https://code.visualstudio.com/) e l'estensione [PlatformIO](https://platformio.org/).

Il framework principale utilizzato rimane comunque Arduino. 

![Thrust Logo](https://github.com/thrust-team/electronics/blob/main/Test%20Stand/Figures/logo_thrust.png)


