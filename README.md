# Setup Raspberry
Kom igång med din mest dammiga pryl. 

## Om RPi
* De äldre modellerna fungerar fint för att komma igång med RPi. 
* Officiell webb är https://www.raspberrypi.org/
* RPi drivs med 3.3V via inbyggd spänningsregulator (matas med 5V från USB)
* OS finns bl.a. från Linux distros, Microsoft och många fler
* Vanligt att anslutning sker via SSH (terminal) eller Remote Desktop 

## Installera Rasbian
Du behöver...
* SD-kort >4GB och minst class 10 (>10 MB/s)
* USB-kabel mellan RPi och dator
* USB laddare (Pi3 model B kräver minst 2.5A, alla andra 1A)
* RPi (gärna Pi3 model B för dess möjlighet till inbyggt WiFi https://www.raspberrypi.org/products)
* Dator ansluten till Internet

### Setup
1. Raspbian är en omskrivning av Debian (Linux dist)
2. Ladda ned https://downloads.raspberrypi.org/raspbian_latest (fullvärdiga versionen)
3. Ladda samtidigt ned och installera Etcher från https://etcher.io/
4. Anslut SD kortet till din dator, inte RPi
5. Starta Etcher och markera nedladdade Rasbian-filen i zip/img-form
6. Välj den disk du vill skriva till (OBS! Gör inte fel här!)
7. Klicka ```Flash!```
8. Flytta SD-kortet till RPi
9. Anslut mus, tangentbord och skärm
10. Spänningsanslut
11. Logga in med USR: ```pi```, PWD: ```raspberry```
