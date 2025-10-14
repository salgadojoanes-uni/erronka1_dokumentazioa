# Sistema Banatuak

### 1. Sistema Banatu baten beharra

Metal-fabrikak bere jarduera digitala handitu ahala, beharrezkoa bihurtu da barne-zerbitzuak modu banatuan antolatzea, bai segurtasuna handitzeko, bai kudeaketa erraztu eta errendimendua optimizatzeko.

Lehen, enpresako bulegoak, kalitatea eta ekoizpen-sailak sare bakar batean ari ziren lanean, eta zerbitzu guztiak makina bakar batean zentralizatuta zeuden. Horrek hainbat arazo zekartzan:

* Baliabide gehiegi kontsumitzen zituen ekipo bakarra.\

* Sareko arazo batek zerbitzu guztiak geldiaraz zitzakeen.\

* Zibersegurtasun maila baxuagoa zen, zerbitzuak ez baitzeuden isolatuta.\


Horregatik, erabaki da sistema banatu bat ezartzea, non zerbitzu bakoitzak bere ingurune birtual propioa izango duen.\
Horri esker, enpresak lortzen du:

* Erabilgarritasun handiagoa: zerbitzu batek huts egiten badu, gainerakoek jarraitzen dute.\

* Segurtasuna: inguruneak isolatuta daude (faila bakar batek ez du besteak kutsatzen).\

* Kudeaketa erraztua: backup eta mantentze-lanak modulu independenteetan.\

* Eskalatzea: etorkizunean beste zerbitzu batzuk gehitzea erraza da.\


Sistema hau ezarri da enpresaren barne-azpiegitura banatzeko, Jitsi Meet barne-bileretarako eta Apache web zerbitzaria dokumentazio eta intranet korporatiborako erabiliz.

2\. Birtualizazio tresnaren ezaugarriak

Sistema banatua Proxmox Virtual Environment oinarrituta dago, birtualizazio-plataforma sendo eta malgua delako.\
Proxmoxek aukera ematen du makina birtualak (VM) eta edukiontzi arinak (LXC) batera kudeatzeko, eta administrazio zentralizatua eskaintzen du web interfazearen bidez.

#### Proxmox plataformaren ezaugarriak

| Ezaugarria           | Balioa                                   |
| -------------------- | ---------------------------------------- |
| Izena                | Proxmox Virtual Environment 8.x          |
| Sistema eragilea     | Debian 12 oinarritua                     |
| Sarea                | VLAN 71 (barneko sarea)                  |
| IP helbidea          | 192.168.x.10 (adib.)                     |
| Birtualizazio mota   | VM + LXC konbinatua                      |
| Kudeaketa protokoloa | SSH eta web interfazea (port 8006)       |
| Babes sistema        | Snapshot + backup automatikoak           |
| Segurtasuna          | SSH sarbide pasahitz/edota gako bidezkoa |

Proxmox plataformak bere gain du VM eta LXC edukiontzien monitorizazioa, baliabide banaketa dinamikoa eta sare birtual propioa VLAN 71 barruan.\
Horri esker, zerbitzu bakoitza isolatuta baina konektatuta dago sare barneko beste osagaiekin.

3\. Birtualizatuko diren zerbitzuak

Sistema banatuan bi zerbitzu nagusi ezarri dira, bakoitza bere ingurune birtualean:

| Zerbitzua              | Birtualizazio mota   | Sistema Eragilea      | Funtzioa                               | IP adibidea  | Azalpena                                                                                 |
| ---------------------- | -------------------- | --------------------- | -------------------------------------- | ------------ | ---------------------------------------------------------------------------------------- |
| Jitsi Meet             | VM (makina birtuala) | Ubuntu Server 24.04.3 | Bilerak eta komunikazio bideo bidezkoa | 192.168.x.11 | Enpresako barne-bileretarako, ez du kanpo sarbiderik, barneko erabiltzaileentzat soilik. |
| Apache Web Zerbitzaria | LXC (edukiontzia)    | Ubuntu 24.04          | Web eta intranet zerbitzua             | 192.168.x.12 | Barneko dokumentazioaren eta komunikazioaren zerbitzua. Enpresako intranetaren oinarria. |

Gainera, Proxmox hostean SSH zerbitzua aktibatuta dago administrazio eta mantentze lanetarako, eta bertatik egiten dira:

* Zerbitzuen monitorizazioa.\

* Backup-en exekuzioa eta berreskurapena.\

* Edukiontzien eta VM-en kontrola.

#### Sarearen egitura laburbilduta

\[VLAN 71 - Barneko Sarea]

├── 192.168.x.10 → Proxmox (host) + SSH + kudeaketa

├── 192.168.x.11 → VM (Ubuntu 24.04.3) → Jitsi Meet zerbitzua

└── 192.168.x.12 → LXC (Ubuntu 24.04) → Apache Web zerbitzaria

4\. Sistema banatuaren funtzionamendua eta abantailak

#### Funtzionamendua:

1. Proxmox plataformak barneko VLAN 71n sare birtual bat sortzen du.\

2. Bi nodo (VM eta LXC) konektatuta daude sare horretan.\

3. Jitsi Meet VMak komunikazioak eta streaming kudeatzen ditu.\

4. Apache edukiontziak web edukia eta barne-dokumentazioa eskaintzen ditu.\

5. Administratzaile orokorrak SSH bidez kudeatzen du guztia Proxmoxetik.\


#### Abantaila nagusiak:

* Zerbitzuen isolamendua: arazo batek ez du beste zerbitzurik eragiten.\

* Segurtasuna: VLAN bereizi batean, kanpoko sarbiderik gabe.\

* Mantentze sinplifikatua: snapshot bidezko backup eta rollback azkarrak.\

* Eskalatzea: etorkizunean beste VM edo LXC bat gehitu daiteke (adib. DNS, DHCP edo Nextcloud).\

* Monitorizazioa eta log zentralizatua: Proxmoxetik zuzenean ikusgai.\


5\. Ondorioa

Sistema banatu hau ezarri da metal-fabrikaren barne-azpiegitura digitala optimizatzeko.\
Proxmox plataforman oinarritutako arkitektura honek eskaintzen du:

* Segurtasun handiagoa (ingurune isolatuak VLAN bereizi batean).\

* Egonkortasuna eta eskalagarritasuna (zerbitzu independenteak).\

* Eta kudeaketa zentralizatua SSH eta web interfazearen bidez.\


Horrela, enpresak lortu du bere zerbitzuak (Jitsi Meet eta Apache) modu banatuan, fidagarrian eta kontrolatuan exekutatzea, sistema banatu moderno eta jasangarri baten oinarriak ezarriz.

\
