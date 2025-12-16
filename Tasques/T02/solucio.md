# T02: DPR: còpies de seguretat. Cas pràctic

PART 1: Windows 11 + Duplicati

Haurem de configurar una maquina virtual Windows afegint un disc dur (virtual) de 10 GB per a les còpies.

![captura1](img/1.png)

També crearem un nou compte de google drive per tenir espai d’emmagatzematge.

![captura2](img/2.png)

Seguidament accedim a la web duplicati.com/download I descarguem duplicati per a Windows.

![captura3](img/3.png)

Un cop instal·lat, l’obrim i se’ns obrirà la web/app. En cas que no s’obri automàticament, hi accedirem des de l’URL següent:

http://127.0.0.1:8200/ngclient/

![captura4](img/4.png)

Un cop hi accedim per primer cop, se’ns demanarà introduir una contrasenya. Un cop desada, ja estarem dins de la interfície.

![captura5](img/5.png)

Ara crearem un nou backup des d’aquesta eina.

![captura6](img/6.png)

Seguirem els passos indicats i introduirem el nom, la descripció, el xifratge, la contrasenya…

![captura7](img/7.png)

Seleccionem la destinació del nostre sistema (File System).

![captura8](img/8.png)

Seguidament, haurem de seleccionar la ruta del nostre disc on guardarem les còpies. En cas que no aparegui el nostre disc, haurem d’inicialitzar-lo tal com vam aprendre al primer curs.

![captura9](img/9.png)

Haurem de seleccionar quines dades o d’on s’hauran de extreure les dades.

![captura10](img/10.png)

Farem clic a **Següent** i escollirem quan s’executarà la còpia.

![captura11](img/11.png)

Seguidament, haurem d’afegir l’opció **passphrase** per introduir una contrasenya. També haurem d’afegir l’opció **snapshot-policy**.

![captura12](img/12.png)

Ara podrem observar com ja tenim aquest backup creat correctament, l’executarem per provar el correcta funcionament.

![captura13](img/13.png)

Un cop el procés ha finalitzat si obrim l’explorador d’arxius podem observar com s’han guardat les dades de forma xifrades.

![captura14](img/14.png)
![captura15](img/15.png)


Ara veurem com fer còpies de seguretat a Google Drive.

Crearem un nou backup, però aquest cop seleccionarem com a destinació **Google Drive**.
