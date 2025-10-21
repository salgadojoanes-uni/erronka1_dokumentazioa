---
icon: desktop
---

# Hardware

\


Oinarrizko plaka

| mota                              | xehetasun                                                                         | Komandoa                                    |
| --------------------------------- | --------------------------------------------------------------------------------- | ------------------------------------------- |
| Fabricante placa base             | ASRock                                                                            | sudo dmidecode -t 2                         |
| Modelo placa base                 | H81M-VG4 R3.0                                                                     | sudo dmidecode -t 2                         |
| Factor de forma                   | Micro-ATX                                                                         | sudo dmidecode -t 2 /                       |
| Tipo de socket CPU                | Intel LGA1150                                                                     | sudo dmidecode -t 4                         |
| CPU soportada                     | 4ta y 5ta generación Intel Core / i3 / i5 / i7 / Xeon                             | sudo dmidecode -t 4 /                       |
| Memoria RAM soportada             | DDR3 1333/1600 MHz                                                                | sudo dmidecode -t 16 / sudo dmidecode -t 17 |
| Máximo RAM                        | 16 GB                                                                             | sudo dmidecode -t 16                        |
| Número de ranuras RAM             | 2 DIMM                                                                            | sudo dmidecode -t 17                        |
| Placa reemplazable                | Sí                                                                                | sudo dmidecode -t 2                         |
| Tipo de chasis                    | Desktop (información genérica)                                                    | sudo dmidecode -t 3                         |
| Número de fuentes de alimentación | 1                                                                                 | sudo dmidecode -t 3                         |
| Estado de PSU / thermal / boot    | Safe                                                                              | sudo dmidecode -t 3                         |
| Fabricante BIOS/UEFI              | American Megatrends Inc.                                                          | sudo dmidecode -t 0                         |
| Versión BIOS                      | P1.20C                                                                            | sudo dmidecode -t 0                         |
| Revisión BIOS                     | 4.6                                                                               | sudo dmidecode -t 0                         |
| Fecha BIOS                        | 28/11/2016                                                                        | sudo dmidecode -t 0                         |
| UEFI soportado                    | Sí                                                                                | sudo dmidecode -t 0 y ls /sys/firmware/efi  |
| Arranque actual                   | UEFI si existe /sys/firmware/efi, sino Legacy BIOS                                | ls /sys/firmware/efi                        |
| Tamaño ROM BIOS                   | 4 MB                                                                              | sudo dmidecode -t 0                         |
| Características BIOS destacadas   | ACPI, USB legacy, BIOS boot spec, Upgradeable, Shadowing permitido, PCI soportado | sudo dmidecode -t 0                         |
| Número de serie placa base        | M80-69022200976                                                                   | sudo dmidecode -t 2                         |
| Estado general del sistema        | Safe                                                                              | sudo dmidecode -t 3                         |

\
\


PUZ

\


| Mota       | xehetasun                     | Komando             |
| ---------- | ----------------------------- | ------------------- |
| Frecuencia | Base: 3.20 GHz, Máx: 3.40 GHz | lscpu               |
| Núcleos    | 4 físicos, 4 hilos            | lscpu               |
| Socket     | LGA1150                       | sudo dmidecode -t 4 |
| Overclock  | No (frecuencia ≤ máxima)      | lscpu               |
| Generación | 4ta generación (Haswell)      | lscpu               |

\
\


RAM

\


| MOTA                                         | XEHETASUNA                                                              |
| -------------------------------------------- | ----------------------------------------------------------------------- |
| Tipo (mota)                                  | DDR3 Synchronous                                                        |
| Cantidad (kopurua)                           | 2 módulos de 4 GB → 8 GB total                                          |
| Frecuencia (Speed / Configured Memory Speed) | 1600 MT/s                                                               |
| Latencia (CAS)                               | CL9 (según Part Number Kingston 99U5584-009.A00LF)                      |
| Form Factor                                  | DIMM                                                                    |
| Marca (Manufacturer)                         | Kingston                                                                |
| Rank                                         | 1 (single rank)                                                         |
| Locator / Bank                               | <p>ChannelA-DIMM0 / BANK 0</p><p>ChannelB-DIMM0 / BANK 2</p><p><br></p> |

\


HDD/SSD

\


Disko gogor bakarra(HDD) 500GB.&#x20;

Hornitzailea: Western Digital&#x20;

Irakurtzeko abiadura: 518 MB en 3.01 sec = 172.08 MB/sec&#x20;

Disko gogorraren barruan 3 partizio egingo ditugu.

\


Elikadura iturria:                                             Komandoa:

Model: Corsair RM650x                                dmesg | grep -i ipmi

\
\


Input: 100-240V \~

Output: 650W

80 PLUS Gold

\
\
\


Txasisa:

Micro-atx                                   dmidecode -t baseboard + Product Name

\
\
\
\


Txartel Grafikoa:

\


| Eremua                      | Balioa                                                                                                                           |
| --------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| Grafiko txartela            | Intel Xeon E3-1200 v3 / 4th Gen Core iGPU                                                                                        |
| Mota                        | Integratua (iGPU)                                                                                                                |
| Driver                      | i915                                                                                                                             |
| Dedikatutako memoria (VRAM) | \~256 MB                                                                                                                         |
| Partekatutako memoria       | <p>BIOSen konfigurazioaren arabera, normalean 1–2 GB RAM erabil daiteke sistema nagusitik</p><p><br><br><br><br><br><br><br></p> |

Disquetera:&#x20;

Una disquetera ISST.corp&#x20;

\


Disipadorea:

intel E97378-003

\


Haizegailua:

Ez dauka

\




\
\
\
\


Hardware hau hautatu dugu:

Birtualizazioarekin bateragarritasuna: Intel CPU VT-x/VT-d-rekin, UEFI, eta RAM nahikoa.\
\


Egonkortasuna: probatutako eta fidagarria den hardwarea (BIOS safe, PSU kalitatezkoa, overclock gabe).\
\


Energia-eraginkortasuna eta kostu arrazionala: DDR3 eta Haswell CPUak gutxi kontsumitzen dute alternatiba modernoak baino.\
\


Etorkizunean handitzeko aukera mugatua baina laborategientzat nahikoa: 16 GB arteko RAM, biltegiratze gehigarria.\
\


Muntaketa eta kudeaketa erraza: Micro-ATX txasisa eta GPU integratua Proxmox instalazioa sinplifikatzen dute.

\
\
\


SOFTWARE:

Jitsi, windows server, ubuntu server, Mariadb, XAMPP, Github, Gitbook, Proxmox eta wordpress, antivirus(windows defender)

\


Proxmox: birtualizazio-servidorea, VMak eta kontenedoreak sortzeko eta kudeatzeko erabili dugu. Muntatu dugun serverrean instalatu dugu pendrive batekin.\
\


Ubuntu Server: zerbitzari arina, MariaDB, WordPress edo Jitsi bezalako zerbitzuetarako  erabili dugu. Isard makinetan instalatu dugu.\
\
\


Windows Server: probetarako eta Windows-ekiko zerbitzu berezietarako zerbitzaria erabili dugu. Isard makinetan instalatu dugu.\
\


MariaDB/XAMPP: datu-baseak eta aplikazioentzako web zerbitzaria erabili dugu. Localhost instalatu dugu\
\
\


WordPress: Apache/MySQL gainean instalatutako CMS webguneetarako erabili dugu. Localhost instalatu dugu.\
\
\


Jitsi: bideo-konferentzia zerbitzu autokudeatua erabili dugu. Ubuntu serbitzarian instalatu dugu\
\
\


GitHub/GitBook: kodea eta dokumentazioa kudeatzeko erabili dugu. Localhost instalatu dugu.\
.

\


### Beharrezko tresna fisikoak

| Tresna                                   | Erabilera nagusia                                                                |
| ---------------------------------------- | -------------------------------------------------------------------------------- |
| Phillips #2 (PH2) giltza-irristagailua   | Kaxa irekitzeko eta plaka, PSU, HDD eta CPU disipadorea finkatzeko               |
| Antiestatikozko eskumuturra (ESD)        | CPU, RAM eta plaka nagusiaren deskarga elektrostatikoak saihesteko               |
| Pasta termikoa + alkohola (isopropiliko) | CPU disipadorea muntatu/berrezarri eta bero-transferentzia egokia ziurtatzeko    |
| Pinzak meheak (aukera)                   | Tornu txikiak jartzeko edo jumpers/kable delikatuak konektatzeko/deskonektatzeko |
| USB booteablea Proxmox ISOarekin         | Proxmox HDD-an instalatzeko                                                      |

\
\
\


Laneko arriskuen prebentzioari eta ingurumen-babesari buruzko arauak

\
\


Hondakinen sistema:

Hondakin organikoen gunea: marroia\
\


Hondakin birziklagarrien gunea (papera, plastikoa, beira): urdina eta horia\
\


Hondakin arriskutsuen gunea: gorria\
\


Hondakin guztiak dagokion edukiontzian utzi behar dira\
\


Hondakinen sistemaren arduraduna: Departamentu Burua.

\
\


&#x20;Ikastetxetik ateratzea:

Erredukzio-bidea adierazitako geziekin (gorriz)\
\


Larrialdi-irteerak argi eta garbi adierazita\
\


Segurtasun eta ebakuazio arduraduna:EcoGestión S.A.

\
\
\


## Tailerraren kontsumo elektrikoaren kudeaketa eta murrizketa

\


Zenbat gastatzen dugun neurtzea: tailerraren hileko kontsumoa neurtu entxufe adimendunak erabiliz edo gailu bakoitzaren potentzia kalkulatuz.\
\


Helburua: kontsumoa %25 murriztea (≈110 kWh/hileko → ≈85 kWh/hileko).\
\


Zer egingo dugu murrizteko: erabilerarik gabeko gailuak itzali, LED argiak erabili eta karga handiko lanak (3D inprimagailua, backup-ak) ordu planifikatuetan egin.\
\


Noiz neurtuko dugu: hilean behin, aurrerapena kontrolatzeko eta ekintzak egokitzeko.

\
