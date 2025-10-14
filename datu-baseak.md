---
icon: cloud-binary
---

# Datu Baseak

## 1. DBKSren aukeraketa:

Proiektu honetarako MariaDB terminaletik instalatua aukeratu dugu. XAMPP paketeak ere MariaDB/MySQL dakarren arren, horrek Apache eta PHP bezalako beste osagai batzuk ere biltzen ditu, eta horrek sistema astunagoa eta batzuetan ezegonkorragoa bihurtzen du. Terminal bidezko instalazio zuzenarekin sistema arinagoa, egonkorragoa eta konfigurazioan kontrol handiagoa lortzen dugu.

## 2. Aukeratutakoaren alde onak eta txarrak honakoak dira:

Alde onak:

* Kode irekia eta doakoa, ez da lizentzia ordaindu beharrik.
* MySQL-ekin bateragarria, migrazioak edo aplikazioen integrazioa errazten du.
* Komunitate eta dokumentazio zabala: foro, eskuliburu eta online laguntza ugari dago.
* Errendimendu ona irakurketa-eragiketetan eta kontsulta konplexuetan.
* Eguneratze eta laguntza jarraitua.
* Instalazio arina, baliabide gutxirekin ere erabil daiteke.

Alde txarrak:

* MySQL baino gutxiago erabiltzen da enpresa handietan (nahiz eta gero eta gehiago hedatzen ari den).
* Ez ditu funtzio aurreratu guztiak (Oracle edo SQL Server bezalako sistema komertzialetan daudenak).
* Ezagutza tekniko handiagoa behar du, terminal bidez kudeatzen delako.

Laburbilduz, MariaDB aukera sendoa, ekonomikoa eta eskalagarria da, nahiz eta administrazio tekniko gehiago eskatu.

## 3. Honetarako hardware-eskakizunak eta baliabide ekonomikoak:

MariaDB zerbitzari baterako gutxieneko baldintzak (enpresa txiki baterako):

* Prozesatzailea: 2 nukleoko CPU (Intel i3/i5 edo AMD baliokidea).
* RAM memoria: 4 GB (hobeto: 8 GB).
* Biltegiratzea: 50 GB SSD (hobeto: NVMe SSD abiadura handiagoa izateko).
* Sistema eragilea: Linux (Ubuntu/Debian).

Kostuak:

* Softwarea: 0 € (MariaDB doakoa da).
* Hardwarea: Ordenagailu edo zerbitzari zahar bat berrerabiliz → kostu minimoa. Zerbitzari fisiko berri bat erosiz → 500 € inguruan. Hodeiko zerbitzaria erabiliz (AWS, Azure, OVH, …) → 10 € – 50 €/hileko instantiaren tamainaren arabera.

## 4. DBKSren instalazioa:

Sistema: Ubuntu Server 24.04.1.

Komandoak:

* sudo apt update
* sudo apt install mariadb-server -y
* sudo systemctl enable --now mariadb
* sudo mysql\_secure\_installation

mysql\_secure\_installation aukerak (erabili ditugunak):

* Root pasahitza ezarri.
* Anonymous erabiltzaileak kendu (Y).
* Root urrunetik sartzea baimendu (Disallow root login remotely? → N).
* Test datu-basea kendu (Y).

## 5. ntzidentziak konpondu ditu eta behar bezala funtzionatzen duela egiaztatu du:

Ez dugu inzidentziarik eduki eta behar bezala funtzionatzen du.

<p align="center"><img src=".gitbook/assets/unknown (14).png" alt="" data-size="original"></p>

## 6. Erregistro-fitxategien eta errore-mezuen informazioa azaldu du:

Goiko berdina.

## 7. Lehenetsitako ezaugarriak (portuak, erabiltzailea...) eta zerbitzua pizteko/itzaltzeko baldintzak:

Portua: 3306

Erabiltzaile lehenetsia: root (password bidez)

Datuen konfigurazioa: /var/lib/mysql

Konfigurazioa: /etc/mysql/mariadb.conf.d/50-server.cnf

* Urrunetik onartzeko: bind-address = 0.0.0.0

Zerbitzua “mariadb” piztu/itzaltzeko etc:

* sudo systemctl start|stop|restart mariadb&#x20;
* sudo systemctl enable|disable mariadb &#x20;

Firewall-a IP-z mugatua:

* sudo ufw allow from 192.168.10.14 to any port 3306 (IP hori gure wordpress zerbitzarikoa da)

## 8. Konexioei buruzko parametroak:

Host: 192.168.10.12

Portua: 3306

Datu Base izena: burdinola\_db

Adibidea: mysql -h 192.168.10.12 -P 3306 -u bulegoak1 -p burdinola\_db &#x20;

## 9. Erabilitzen ari den errekurtsoak:

Zerbitzuaren egoera ikusteko: systemctl status mariadb

Portua irekita dagoen: ss -lntp | grep 3306

CPU/RAM-aren erabilera: top / htop / ps aux | grep mysqld

## 10. Erabilitako erabiltzaile eta baimenak:

Guztira 10 erabiltzaile aukeratu ditugu, guretzat optimoa dena, 3 departamentu bakoitzeko, hau da, 9 guztira eta beste 1 administratzaile generala izango dena. Horiek nahikoak dira guk behar duguna administratzeko. Ondorengoak izango ziren:

### **Root**

| Erabiltzailea | Pasahitza     | Baimenak |
| ------------- | ------------- | -------- |
| root          | Mari@db123\$$ | Dena     |

### Admin Generala

| Erabiltzailea    | Pasahitza           | Baimenak |
| ---------------- | ------------------- | -------- |
| burdinola\_admin | Burdinol@123\$$\_db | Dena     |

### Bulegoak

| Erabiltzaileak | Pasahitza         | Baimenak                                             |
| -------------- | ----------------- | ---------------------------------------------------- |
| bulegoak1      | Bulego@123\$$\_db |       select,insert,create, update,update,drop index |
| bulegoak2      | Bulego@123\$$\_db |       select,insert,update                           |
| bulegoak3      | Bulego@123\$$\_db |       select,insert,update                           |

### Kalitatea

| Erabiltzaileak | Pasahitza           | Baimenak                                               |
| -------------- | ------------------- | ------------------------------------------------------ |
| kalitatea1     | Kalitate@123\$$\_db |         select,insert,create, update,update,drop index |
| kalitatea2     | Kalitate@123\$$\_db |         select,insert,update                           |
| kalitatea3     | Kalitate@123\$$\_db |         select,insert,update                           |

### Produkzioa

| Erabiltzaileak | Pasahitza            | Baimenak                                       |
| -------------- | -------------------- | ---------------------------------------------- |
| produkzioa1    | Produkzio@123\$$\_db | select,insert,create, update,update,drop index |
| produkzioa2    | Produkzio@123\$$\_db | select,insert,update                           |
| produkzioa3    | Produkzio@123\$$\_db | select,insert,update                           |

### Rolak

| Rolak       | Erabiltzaileak                                                        |
| ----------- | --------------------------------------------------------------------- |
| taldeburuak | produkzioa1, kalitatea1, bulegoak1                                    |
| langileak   | bulegoak2, bulegoak3, produkzioa2, produkzioa3, kalitatea2, kalitatea |
