---
icon: sitemap
---

# Sistema eragileak

###

## GPO

### CMD bloqueo

![](<.gitbook/assets/unknown (53).png>)

klik eskuina domeinuaren izenean eta gpo berri bat sortu.

\
![](<.gitbook/assets/unknown (54).png>)

araua aplikatzea nahi dugun erabiltzaile/taldeak sartuko ditugu

![](<.gitbook/assets/unknown (55).png>)\


eskuineko click, eta sortutako gpo-a editatzen dugu. Gero joan: Configuracion de usuario, directivas, plantilla administrativas, sistema eta click eskuina en impedir el acceso al simbolo del sistema, baimentzen dugu. Azkenik erabiltzaile batean konporbatzen dugu.

![](<.gitbook/assets/unknown (56).png>)

### FONDO

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

![](<.gitbook/assets/unknown (67).png>)![](<.gitbook/assets/unknown (68).png>)\
\


###

## CUPS

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
