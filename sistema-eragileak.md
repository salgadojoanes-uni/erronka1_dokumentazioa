---
icon: sitemap
---

# Sistema eragileak

#### **Domeinuaren egitura eta zerbitzariaren informazioa**

**Domeinua:** `burdinola.lan`\
**Zerbitzari nagusia:** `BUR-WINSERVER`\
**IP:** `192.168.10.10`

## **1. Domeinuko OU-ak, erabiltzaileak eta taldeak**

Lehenik domeinuan burdinola izeneko OU bat sortu dugu gero bertan barruan departamentu bakoitzeko  beste bat jartzeko:

bulegoak OU

1. **bulegoak taldea**
   * Erabiltzaileak: _bulegoak1, bulegoak2, bulegoak3_

kalitatea OU

1.  **kalitatea taldea**

    * Erabiltzaileak: _kalitatea1, kalitatea2, kalitatea3_



produkzioa OU

1. **produkzioa taldea**
   * Erabiltzaileak: _produkzioa1, produkzioa2, produkzioa3_

Gainera, **taldeburuak** izeneko OU bat dago, non talde bakoitzeko buruak edo jefeak (_bulegoak1, kalitatea1, produkzioa1_) biltzen diren.

<figure><img src=".gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

### **OU egituraren arrazoia**

OU egitura hau sortu dugu **sail edo departamentu bakoitzaren arabera kudeaketa errazteko**.\
Horrela:

* Politika eta baimen desberdinak aplikatu daitezke sail bakoitzean.
* Taldeburuak OU berezian bildu dira, administrazio edo kudeaketa-eskubide handiagoak izateko.
* Egitura argiak mantentzen du sareko antolaketa eta segurtasuna.

### **Zerbitzariaren zerbitzuak (ROLak)**

`BUR-WINSERVER` zerbitzariak honako **zerbitzu eta rolak** eskaintzen ditu:

* **Active Directory Domain Services (AD DS)**
* **DNS zerbitzaria** (domeinuko izenak ebazteko)
* **DHCP zerbitzaria** (IP helbideak automatikoki esleitzeko)
  * Rangoa: `192.168.10.100 – 192.168.10.200`
* **Fitxategi- eta inprimagailu-zerbitzua**
* **Bideo-zerbitzua (Jitsi Meet)**, Ubuntu zerbitzarian (IP: `192.168.10.11`)
* Proxmox ip-a --> **192.168.10.14**
* Ubuntu server ip-a Cups --> **192.168.10.15**
* Bulegoak1,2,3 ip-a --> **DHCP 192.168.10.100<-->200**
* Kalitatea1,2,3 ip-a --> **DHCP 192.168.10.100<-->200**
* Produkzioa1,2,3 ip-a --> **DHCP 192.168.10.100<-->200**

## **2. Erabiltzaileen Konfigurazioa**

**Hemen ikusten dugu nola bulegoak1 erabiltzaileak domeinuko ip tarte batean dagoen, dns bezala 192.168.10.10 duen eta domeinu barruan nola dagoen. Hau bulegoak OU barruan dago goian ikusi dugun bezala. Beste erabiltzaileak berdin.**

<figure><img src=".gitbook/assets/image (1) (2).png" alt=""><figcaption></figcaption></figure>

## 3. GPO Pertsonalizatuak

### CMD erabilera blokeatu

![](<.gitbook/assets/unknown (53).png>)

klik eskuina domeinuaren izenean eta gpo berri bat sortu.

\
![](<.gitbook/assets/unknown (54).png>)

araua aplikatzea nahi dugun erabiltzaile/taldeak sartuko ditugu

![](<.gitbook/assets/unknown (55).png>)\


eskuineko click, eta sortutako gpo-a editatzen dugu. Gero joan: Configuracion de usuario, directivas, plantilla administrativas, sistema eta click eskuina en impedir el acceso al simbolo del sistema, baimentzen dugu. Azkenik erabiltzaile batean konporbatzen dugu.

![](<.gitbook/assets/unknown (56).png>)

### Fondoa

![](<.gitbook/assets/unknown (60).png>)

Baimentzen dugu active desktop.

![](<.gitbook/assets/unknown (58).png>)

karpeta bat sortzen dugu. Barruan gure imagena sartzen dugu. Ondoren ematen diogu a compartir la carpeta.

![](<.gitbook/assets/unknown (61).png>)

GPO berri bat egiten dugu, Fondo deitzen dena. ondoren berriro partekazten dugu nahi dugun erabiltzaileekin

![](<.gitbook/assets/unknown (62).png>)

Gero editatzen dugu sortutako GPO berria.

![](<.gitbook/assets/unknown (63).png>)

Habilitzen dugu active desktop eta ondoren tapiz del escritorio ere. En tapiz del escritorio ipini behar dugu gure argazkiaren kokapena. ADB:

![](<.gitbook/assets/unknown (64).png>)

En la parte de nombre del papel tapiz tienes que escribir el nombre de la foto que en la captura no se ve.

![](<.gitbook/assets/unknown (65).png>)

Erabiltzaile batera joaten gara eta ikusten dugu.

![](<.gitbook/assets/unknown (66).png>)

### Pasahitza

(8 karakter minimo, karakter especiales, 1 egun mini aldatu ahal izateko, 30 egun adatu obligatorio)

![](<.gitbook/assets/unknown (67).png>)![](<.gitbook/assets/unknown (68).png>)

## 4. Inprimagailuen Informazioa

### **Portuak eta Protokoloak**

#### **Windows sistemetan**

Windows sistemetan inprimaketa-zerbitzua (Print Server) **TCP/IP** bidez funtzionatzen du:

* **Protokolo nagusiak:**
  * **SMB (Server Message Block)** — inprimagailu partekatuetarako
  * **RAW (portua 9100)** — AppSocket/JetDirect motako inprimagailuak
  * **IPP (Internet Printing Protocol, portua 631)** — inprimagailu modernoak eta web bidezko zerbitzua
  * **LPD/LPR (portua 515)** — sistema zaharragoekin bateragarritasuna

#### **Linux sistemetan**

Linux-en **CUPS** (Common UNIX Printing System) erabiltzen da:

* **Protokoloak:**
  * **IPP (631/tcp)** — oinarrizko inprimaketa-protokoloa
  * **AppSocket / HP JetDirect (9100/tcp)**
  * **LPD/LPR (515/tcp)**
* **Administrazio web ataria:**
  * `http://192.168.10.15:631` (Cups Ubuntu Zerbitzaria)

### Inprimagailuak

#### **Izena eta haien kokapena**

<table><thead><tr><th width="250.20001220703125">Inprimagailua</th><th width="258.5999755859375">Zerbitzaria / IP</th><th>Kokapena</th></tr></thead><tbody><tr><td>b<strong>ulegoak_inprimagailua</strong></td><td><code>\\192.168.10.10\Bulegoak</code></td><td>Bulego nagusia</td></tr><tr><td><strong>kalitatea_inprimagailua</strong></td><td><code>\\192.168.10.10\Kalitatea</code></td><td>Kalitate saila</td></tr><tr><td><strong>produkzioa_inprimagailua</strong></td><td><code>\\192.168.10.10\Produkzioa</code></td><td>Produkzio gunea</td></tr></tbody></table>

#### **Taldeei esleitutako baimenak**

| Taldea / OU    | Inprimagailua             | Baimena             |
| -------------- | ------------------------- | ------------------- |
| **bulegoak**   | bulegoak\_inprimagailua   | Inprimatu ahal dute |
| **kalitatea**  | kalitatea\_inprimagailua  | Inprimatu ahal dute |
| **produkzioa** | produkzioa\_inprimagailua | Inprimatu ahal dute |







## 5. CUPS

apt-get install cups

![](<.gitbook/assets/unknown (69).png>)![](<.gitbook/assets/unknown (70).png>)



nano /etc/cups/cupsd.conf

![](<.gitbook/assets/unknown (72).png>)

En only listen for connections from the local machine ipintzen dugu gure IP eta azkeno hiruretan ipintzen dugu Allow All

Gero google ipintzen dugu [https://ip\_deñ\_server:631](about:blank)

\


#### Sortu erabiltzaile bat

sudo adduser burdinola\_esora       pasahitza: Burdinol@123\$$

eman baimenak&#x20;

sudo usermod -aG lpadmin burdinola\_impresora&#x20;

getent group burdinola\_impresora

systemctl restart cups&#x20;

gero sartu sortutako erabiltzailearekin

![](<.gitbook/assets/unknown (73).png>)\
\


izena ipintzen diogu, kokalekua eta konpartitzen dugu.

![](<.gitbook/assets/unknown (74).png>)

gero marka aukeratzen dugu.

![](<.gitbook/assets/unknown (75).png>)

inportante agertzea compartida.

![](<.gitbook/assets/unknown (76).png>)

3 inprimagailuak gehitzen ditugu.

![](<.gitbook/assets/unknown (77).png>)

y para un ubuntu literal meter dns, te vas a impresoras y ya estas las 3

![](<.gitbook/assets/unknown (78).png>)![](<.gitbook/assets/unknown (79).png>)\
\
![](<.gitbook/assets/unknown (80).png>)![](<.gitbook/assets/unknown (81).png>)\


Windows impresora

![](<.gitbook/assets/unknown (82).png>)![](<.gitbook/assets/unknown (83).png>)![](<.gitbook/assets/unknown (84).png>)![](<.gitbook/assets/unknown (85).png>)![](<.gitbook/assets/unknown (86).png>)![](<.gitbook/assets/unknown (87).png>)![](<.gitbook/assets/unknown (88).png>)\
