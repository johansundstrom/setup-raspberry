# Setup Raspberry
Kom igång med din mest dammiga pryl i lådan 

## Om RPi
* De äldre RPi-modellerna fungerar finfint att använda så släng dem inte!
* Officiell webb är https://www.raspberrypi.org/
* Senaste modellen heter Pi3 model B och har t.ex. inbyggt WiFi/Bluetooth
* Modellerna presenteras på https://www.raspberrypi.org/products)
* RPi drivs med 3.3V via inbyggd spänningsregulator (matas med 5V från USB)
* OS finns från bl.a. Linux distros, Microsoft och många fler
* Vanligt är att anslutning sker via SSH (terminal) eller Remote Desktop 

## Installera Rasbian
Du behöver...
* SD-kort >4GB och minst class 10 (>10 MB/s)
* USB-kabel mellan RPi och dator (drift och installation)
* För fristående användning krävs USB laddare (Pi3 model B kräver minst 2.5A, alla andra 1A)
* PC/Mac/Linux ansluten till Internet

### Setup
1. Raspbian är en omskrivning av Debian (välkänd Linux dist)
2. Ladda ned https://downloads.raspberrypi.org/raspbian_latest (fullvärdiga versionen ~1.6GB) 
3. Ladda samtidigt ned och installera Etcher från https://etcher.io/ (~50MB)
4. Anslut SD kortet till din dator, inte RPi
5. Notera vilken enhetsbeteckning den får (typ F:)
6. Starta Etcher och markera nedladdade Rasbian-filen i zip/img-form
7. Välj den SD-disken som kommer att formatteras och skrivas över (OBS! Gör inte fel här!)
8. Klicka ```Flash!```
9. Flytta SD-kortet till RPi
10. Anslut mus, tangentbord och skärm
11. Spänningsanslut
12. Logga in med USR: ```pi```, PWD: ```raspberry```
