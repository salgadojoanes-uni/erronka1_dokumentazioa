---
icon: hand-dots
---

# Segurtasuna

Mysql:

Root

Erabiltzailea: root

Pasahitza: Mari@db123\$$



Bulegoak

Erabiltzaileak:                                    Pasahitza:

bulegoak1                                            Bulego@123\$$\_db

bulegoak2                                           Bulego@123\$$\_db

bulegoak3                                           Bulego@123\$$\_db



Kalitatea

Erabiltzaileak:                                    Pasahitza:

kalitatea1                                             Kalitate@123\$$\_db

kalitatea2                                            Kalitate@123\$$\_db

kalitatea3                                            Kalitate@123\$$\_db



Produkzioa

Erabiltzaileak:                                    Pasahitza:

produkzioa1                                        Produkzio@123\$$\_db

produkzioa2                                       Produkzio@123\$$\_db

produkzioa3                                       Produkzio@123\$$\_db



Admin Generala

Erabiltzailea:  burdinola\_admin

Pasahitza: Burdinol@123\$$\_db



Windows server

Erabiltzailea: BURDINOLA

Pasahitza: Admin123



Bulegoak

Erabiltzaileak:                                    Pasahitza:

bulegoak1                                            Bulego@123\$$

bulegoak2                                           Bulego@123\$$

bulegoak3                                           Bulego@123\$$



Kalitatea

Erabiltzaileak:                                    Pasahitza:

kalitatea1                                             Kalitate@123\$$

kalitatea2                                            Kalitate@123\$$

kalitatea3                                            Kalitate@123\$$



Produkzioa

Erabiltzaileak:                                    Pasahitza:

produkzioa1                                        Produkzio@123\$$

produkzioa2                                       Produkzio@123\$$

produkzioa3                                       Produkzio@123\$$



Cups

Erabiltzailea:                                       Pasahitza:

uni                                                          Admin123

root                                                        Cups123\$$



Ubuntu server &#x20;

Erabiltzailea:                                       Pasahitza:

uni                                                          Admin123

root                                                        Admin123







## 1. Enpresaren Deskribapena

Enpresa hau pieza mekanikoen fabrikazioan espezializatutako metal-fabrika da. Bere jarduera nagusia altzairu, aluminio eta bestelako aleazio metalikoekin lan egitea da, eta bezero industrialentzako osagai eta piezak ekoizten ditu.

Fabrika 3 sail nagusitan banatuta dago:

* Bulegoak (Administrazioa eta Kudeaketa): fakturazioa, bezero eta hornitzaileen kudeaketa, dokumentazio digitala eta webgunearen edukia.\
  \

* Kalitatea: produktu bukatuen neurketa, ziurtagiri teknikoak eta trazabilitate digitalaren kontrola.\
  \

* Ekoizpena: CNC makinak, prentsak eta soldadura ekipoak erabiltzen dira, ERP sistemaren bidez lan-ordenen jarraipena eginez.\
  \


Sail bakoitzean 3 langile daude: 1 arduradun eta 2 langile. Horiez gain, badago sistemetako administratzaile orokor bat, enpresaren azpiegitura digitalaren eta zibersegurtasunaren arduraduna.

Azpiegitura informatikoa osatzen dute:

* DNS eta DHCP zerbitzuak (barne-sarearen kudeaketarako).\
  \

* WordPress oinarritutako web korporatiboa.\
  \

* CUPS eta inprimagailu-sare bat, Windows zerbitzarietan oinarritua.\
  \

* Jitsi Meet komunikazio-sistema, bilera birtualetarako.\
  \

* Antibirus zentralizatuak eta pasahitz-politika zorrotza (90 egunero berritzea).\
  \

* Segurtasun kopia automatikoak egunero egiten dira zerbitzarian eta hodeian.\
  \


\


\


2\. Aktiboen Azterketa (INCIBE PILAR metodologiaren arabera)

INCIBEren PILAR tresnak aktiboak hiru mailatan aztertzen ditu: logikoak, fisikoak eta pertsonalak. Hemen da laburpena:

| Aktibo mota | Aktiboa                                  | Garrantzia | Oharrak                                      |
| ----------- | ---------------------------------------- | ---------- | -------------------------------------------- |
| Logikoa     | Zerbitzaria eta segurtasun kopiak        | Altua      | Jardueraren funtsezkoa; datu guztiak bertan  |
| Logikoa     | DNS, DHCP, WordPress, Jitsi zerbitzuak   | Altua      | Sarearen eta komunikazioaren oinarria        |
| Logikoa     | ERP eta bulegoetako datu-fitxategiak     | Altua      | Ekoizpenaren kontrolerako                    |
| Fisikoa     | CNC makinak, prentsak, soldadura-ekipoak | Altua      | Produkzioaren muina                          |
| Fisikoa     | Sareko router eta switch-ak              | Altua      | Zerbitzu guztien komunikazio zirkuitua       |
| Pertsonala  | Langile kualifikatuak eta arduradunak    | Altua      | Ezagutza funtsezkoa da sistemaren erabileran |
| Osagarria   | Internet konexioa eta energia hornidura  | Altua      | Zerbitzuen jarraipena bermatzeko             |

Laburpena: aktibo kritikoen gehiengoa digitala eta komunikazioan oinarritua da; beraz, zibersegurtasuna da lehentasuna.

3\. Arrisku-Kasuak eta Balorazioa

| Arrisku mota                              | Deskribapena                                | Probabilitatea | Eragina   | Maila    |
| ----------------------------------------- | ------------------------------------------- | -------------- | --------- | -------- |
| Ransomware edo zibererasoa                | Datuak enkriptatu eta jarduera eten         | Ertaina        | Oso altua | Kritikoa |
| Sarearen etenaldia (router, DHCP)         | Barne sarearen funtzionamendua gelditzen da | Ertaina        | Altua     | Handia   |
| Langile baten akats edo pasahitz-ihesa    | Sarbide ez-baimendua edo datu lapurra       | Handia         | Ertaina   | Handia   |
| Sute edo kalte fisikoa                    | Zerbitzaria edo makinak kaltetu             | Baxua          | Altua     | Ertaina  |
| Energia elektrikoaren etenaldia           | Zerbitzari eta makinak gelditu              | Ertaina        | Ertaina   | Ertaina  |
| Hardware hutsegitea                       | Disko gogorra edo switch-a hondatu          | Ertaina        | Altua     | Handia   |
| Webgune edo komunikazio zerbitzua erorita | WordPress edo Jitsi offline                 | Handia         | Ertaina   | Handia   |

Ondorio nagusia: arrisku nagusiak logikoak dira (zibererasoak, sare-hutsegiteak, baimen-ihesak). Horiek dira planaren ardatza.

4\. Babes Plana (Larrialdi Aurretik)

#### Helburua:

Arriskuen aurkako prebentzio-neurriak ezartzea eta jardueraren jarraipena bermatzea, bai sistemetan bai langileen praktikan.

Babes Logikoak

1. Antibirus zentralizatua eta EDR sistema: terminal guztiak monitorizatzen dira (ekipoen portaera anormala detektatzeko).\
   \

2. Firewall eta IDS sistema: kanpoko eta barneko trafikoa kontrolatzeko.\
   \

3. Pasahitz-politika zorrotza: 90 eguneko aldaketa-zikloa, gutxieneko 12 karaktere eta bi faktoreko autentifikazioa.\
   \

4. Segurtasun kopia automatikoak:\
   \

5. Zerbitzarian egunero 01:00etan.\
   \

6. Hodeian (enkriptatuta) astero.\
   \

7. Sarearen segmentazioa: bulegoetako sareak eta ekoizpen-sareak bereizita mantentzen dira VLAN bidez.\
   \

8. Erabiltzaileen baimen-mailak: funtzioaren arabera mugatuak, “minimo beharrezkoa” printzipioaren arabera.\
   \

9. Software eguneraketak automatizatuak: Windows eta aplikazio korporatibo guztiak.\
   \

10. Langileentzako zibersegurtasun prestakuntza: phishing simulazioak eta ohiko arriskuen inguruko formazioa hiru hilean behin.

Babes Fisikoak

1. Bideo-zaintza sistema 24/7 fabrikako sarreretan eta datu-zerbitzuen gunean.\
   \

2. Sarbide-kontrola: txartel magnetiko bidezkoa bulegoetan eta zerbitzari-gelan.\
   \

3. Suteen aurkako detektagailuak eta itzalgailuak eguneratuak.\
   \

4. SAI/UPS sistema zerbitzarientzat eta sareko ekipoentzat.\
   \

5. Mantentze prebentiboa: makina industrialak eta sare-ekipamenduak 6 hilean behin berrikusten dira.\
   \


Prebentzio-Prozedurak

* Astean behin, backup-en osotasun-proba egiten da.\
  \

* Hilean behin, log eta alerten berrikuspena egiten da sistemetatik.\
  \

* Urtero, arrisku-analisiaren berrikuspena eta planaren eguneraketa egiten dira.\
  \


5\. Erantzun Plana (Larrialdiaren Garaian eta Ondoren)

#### Erantzun Logikoa

1. Detekzioa eta jakinarazpena:\
   \

2. Administratzaile orokorrak alertak jasotzen ditu EDR edo IDS sistemetatik.\
   \

3. Zibereraso susmoa dagoenean, sarearen segmentua isolatzen da.\
   \

4. Ingurunearen isolamendua:\
   \

5. Zerbitzari kaltetua sare nagusitik deskonektatu.\
   \

6. Ekipamendu susmagarriak karantinan jarri.\
   \

7. Azterketa forentikoa:\
   \

8. Log fitxategiak aztertu (jatorria, denbora, erabiltzailea, IPak).\
   \

9. Eraso mota identifikatu (ransomware, phishing, malware...).\
   \

10. Erabiltzaileen abisua eta koordinazioa:\
    \

11. Bulegoetako eta ekoizpeneko arduradunek jarduera eten.\
    \

12. Langileek ez dute sistemetan saio berririk hasten.\
    \

13. Komunikazioa:\
    \

14. Zuzendaritzak bezero eta hornitzaileei egoeraren berri emango die.\
    \

15. Ez da informazio konfidentzialik partekatuko sare publikoetan.

Erantzun Fisikoa

1. Larrialdia (sute, istripua) gertatuz gero, departamentuko buruak ebakuazioa koordinatuko du.\
   \

2. 112 deitu, eta segurtasun fisikoko protokoloa aktibatu.\
   \

3. Kaltearen jatorria identifikatu eta eremua isolatu.\
   \

4. Segurtasun arduradunak ebaluatuko du instalazioen egoera jarduera berriro hasteko.\
   \


6\. Berreskuratze Plana (Larrialdiaren Ondoren)

Berreskuratze Logikoa

1. Backup berreskurapena: azken segurtasun-kopia erabiliz zerbitzu guztiak lehengoratu.\
   \

2. Sistema garbiketa eta egiaztapena:\
   \

3. Malware eskaneoa eta osotasun-kontrola.\
   \

4. Software eguneraketa berriak aplikatu.\
   \

5. Zerbitzuen leheneratzea:\
   \

6. DNS eta DHCP zerbitzuak lehenik.\
   \

7. Gero, CUPS, Jitsi eta WordPress.\
   \

8. Azkenik, ERP eta bulegoetako aplikazioak.\
   \

9. Segurtasun probak:\
   \

10. Sare eta autentifikazioaren testak.\
    \

11. Log eta trafikoaren analisi azkarra.\
    \

12. Txosten forentikoa eta ikaskuntza:\
    \

13. Gertatutakoaren dokumentazioa eta analisia.\
    \

14. Neurri zuzentzaile eta prebentibo berriak ezarri.

Berreskuratze Fisikoa

1. Kalte fisikoen ebaluazioa eta dokumentazioa.\
   \

2. Gailu hondatuen konponketa edo ordezkapena.\
   \

3. Instalazioen segurtasun elektriko eta mekanikoaren berrikuspena.\
   \

4. Langileentzako formazio laburra larrialdiaren ikasgaietan.\
   \

5. Jarduera pixkanaka berrabiaraztea: lehen fasean funtsezko lanak, ondoren ohiko erritmoa.\
   \


7\. Ondorioak eta Gomendio Estrategikoak

Plan honek helburu argi bat du:\
Enpresaren jarduera digital eta fisikoa etengabe babestea, etenaldi minimoarekin eta datuen osotasuna bermatuz.

Gomendioak:

1. Zibersegurtasunaren aurrekontua mantendu edo handitu, EDR eta SOC zerbitzuekin.\
   \

2. Langileen prestakuntza jarraitua, batez ere phishing eta datu-kudeaketan.\
   \

3. Backup sistema hibridoa mantendu (lokala + hodeia).\
   \

4. Urtero planaren berrikuspena eta zibereraso simulazio bat egitea.\
   \

5. Larrialdi komunikazio-kanal alternatibo bat ezarri (telefono-sare edo aplikazio mugikor bidezkoa).\
   \


Ondorio Orokorra

Fabrika honek ez du soilik instalazioen segurtasuna bermatzen, baizik eta ziberespazioan bere aktibo kritikoen jarraipena eta babesa.\
Plan honen bidez, arrisku gehienak aurreikusi, arindu eta azkar berreskuratzeko moduan egongo da, larrialdi baten aurrean erantzun koordinatua eta eraginkorra eskainiz.

\
