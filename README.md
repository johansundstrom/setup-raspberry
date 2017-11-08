# Setup Raspberry
Kom igång med hobbylådans mest dammiga pryl 

## Om RPi
* De äldre RPi-modellerna fungerar finfint att använda så släng dem inte!
* Officiell webb är https://www.raspberrypi.org/
* Senaste modellen heter Pi3 model B och har t.ex. inbyggt WiFi/Bluetooth
* Modellerna presenteras på https://www.raspberrypi.org/products)
* RPi drivs internt med 3.3V via inbyggda spänningsregulatorn (matas med 5V från USB)
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
6. Starta Etcher och markera nedladdade Rasbian-filen i zip/img-form (UnZip behövs ej)
7. Välj den SD-disken som kommer att formatteras och skrivas över (OBS! Gör inte fel här!)
8. Klicka ```Flash!```
9. Flytta SD-kortet till RPi
10. Anslut mus, tangentbord och skärm
11. Spänningsanslut
12. Logga in med USR: ```pi```, PWD: ```raspberry``` om du inte blir inloggad automatiskt

## Konfigurera
1. Starta terminalen 
2. ```sudo raspi-config```
3. Navigera med piltangeter, enter och esc
4. Ställ in Svensk tid och Svenskt tangentbord layout
5. Möjliggör SSH
6. Lämna och spara

## Uppdatera systemet
* Linux och dess distros uppdateras ständigt. Tag för vana att alltid kontrollera att operativsystemet har senaste uppdateringarna, speciellt inför varje ny app-installation
* För att använda systemt med administrativa rättigheter (skrivning utanför hemkatalogen) inleds kommandon som behöver detta med ```sudo```
* Observera att detta kan ta väldigt lång tid (~20 minuter) beroende på om man ligger efter
* ```sudo apt-get update```
* ```sudo apt-get upgrade```

## Setup File Share och VNC Server
1. ```sudo apt-get update```
2. ```sudo apt-get upgrade```
3. ```sudo apt install -y tightvncserver``` Installerar kompakt VNC Server
4. ```sudo apt install -y xrdp``` Installerar Debians version av RDP-protokollet
5. ```sudo apt install -y samba``` Installerar nätverksprotokollet SMB/CIFS (SMB - därav Samba)
6. ```sudo leafpad /etc/samba/smb.conf &``` Öppna konfigurationsfilen för Samba
7. Lägg till följande i slutet på filen...
```
[PiShare]
 comment=Raspi Share
 path=/home/pi
 browseable=Yes
 writeable=Yes
 only guest=No
 create mask=0740
 directory mask=0750
 public=no
 ```
 ### Fast IP
 1. ```sudo ifconfig -a``` Visa aktuell IP-adress
 2. sudo nano /etc/dhcpcd.conf
 3. Skriv in följande...
```
interface eth0

static ip_address=192.168.0.10/24
static routers=192.168.0.1
static domain_name_servers=192.168.0.1

interface wlan0

static ip_address=192.168.0.200/24
static routers=192.168.0.1
static domain_name_servers=192.168.0.1
```
