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

![captura16](img/16.png)


Un cop avancem, haurem de vincular Duplicati amb Google Drive. Per fer-ho, farem clic sobre l’enllaç **AuthID**.

![captura17](img/17.png)

I iniciarem la sessió amb el nostre compte de Google (nou).

![captura18](img/18.png)

També haurem d’indicar la ruta de la carpeta on volem guardar les dades. Per fer-ho, introduirem la URL al camp **Ruta de la carpeta**.

![captura19](img/19.png)

![captura20](img/20.png)


Seleccionem les mateixes dades com abans.

![captura21](img/21.png)

Definim quan s’executarà, diariament a les 18:00

![captura22](img/22.png)


Afegirem l'opció **passphrase**, igual que abans, amb una contrasenya, i també **snapshot-policy**.

Executem el backup de Google Drive per fer un test.

![captura23](img/23.png)

Al finalitzar podrem confirmar el correcta funcionament revisant la carpeta de google drive.

![captura24](img/24.png)

Ara farem algunes proves de les còpies i restauració, crearem un arxiu dins la ruta del usuari.

Crearem un arxiu dins el nostre directori personal amb la comanda:
```
fsutil file createnew C:\Users\[USUARI]\Documents\test1.txt 10485760
```

![captura25](img/25.png)

Seguidament farem una còpia des de duplicati, borrarem aquest arxiu i restaurarem desde l’eina.

![captura26](img/26.png)

![captura27](img/27.png)

i despres hem de fer el maiteix procediment pero amb el Backup del Drive.

---

# Part 2: Còpia seguretat servidor Linux

igual que a la maquina de Windows, ara tambe crearem un disc a la nostra VM.

![captura28](img/28.png)

Un cop dins la maquina hem de verificar que el detecti.

```
lsblk

```
![captura29](img/29.png)

Creem una partició sobre el nou disc amb la comanda:
```
sudo fdisk /dev/sdb
```
![captura30](img/30.png)


Un cop aparegui el **menú de `fdisk`**, seguirem els següents passos:

1. **`n`** → Crear una nova partició.  
2. **`p`** → Seleccionar que sigui una partició primària.  
3. Prem **Enter** tres vegades per acceptar els valors per defecte.  
4. **`w`** → Guardar els canvis i sortir de `fdisk`.

![captura31](img/31.png)

![captura32](img/32.png)

Formategem el disc en format XFS, pero primer de tot haurem d’instal·lar el servei XFS
```
sudo apt install xfsprogs
```

![captura33](img/33.png)

```
sudo mkfs.xfs /dev/sdb1
```

![captura34](img/34.png)

Acte seguit crearem una carpeta i muntarem el disc a aquesta.

```
sudo mkdir -p /media/backup
sudo mount /dev/sdb1 /media/backup
```

![captura35](img/35.png)


Per comprovar si està muntat correctament utilitzarem la comanda:

```
df -h | grep backup
```
![captura36](img/36.png)


Ara instal·larem duplicity, l’eina per automatitzar les còpies.
```
sudo apt install duplicity -y
duplicity –version
```

![captura37](img/37.png)


Crearem dos usuaris, asegurant-nos que tenen directoris personals.
```
sudo adduser usuari1
sudo adduser usuari2
```

![captura38](img/38.png)


Ara crearem 4 fitxers de 10 MB dins el directori que hem creat anteriorment. for i in 1 2 3 4; do sudo dd if=/dev/zero of=fitxer$i bs=1M count=10; done

![captura39](img/39.png)


Comprovem amb 

```
ls -lh
```

![captura40](img/40.png)

Crearem la copia amb duplicity, ens demana un passphrase (contrasenya) la qual la xifrarà.
```
sudo duplicity /home file:///media/backup/home-backup
```

![captura41](img/41.png)

Al finalitzar, podem observar que hi ha al directori destí.

![captura42](img/42.png)

Seguidament esborrarem els arxius de prova creats anteriorment per veure si els pot restaurar correctament.
```
sudo rm fitxer1 fitxer2 fitxer3 fitxer4
ls
```

![captura43](img/43.png)


Ara restaurarem els arxius amb duplicity
```
sudo duplicity restore file:///media/backup/home-backup /home/restored
ls /home/restored/usuari
```

![captura44](img/44.png)

Executarem la mateixa comanda d’abans per crear la còpia.
```
sudo duplicity /home file:///media/backup/home-backup
```

![captura45](img/45.png)


Podem veure l’informació del backup
```
sudo duplicity collection-status file:///media/backup/home-backup
```

![captura46](img/46.png)

Ara desmontem l’unitat
```
sudo umount /media/backup
```

I comprovem
```
df -h | grep backup
```

![captura47](img/47.png)


Ara automatitzarem tots aquest procesos amb la comanda:
```
sudo nano /root/fullbackup.sh
```
````
#!/bin/bash

mount /dev/sdb1 /media/backup

export PASSPHRASE="la_teva_contrasenya"

duplicity full /home file:///media/backup/home-backup

unset PASSPHRASE

umount /media/backup

````
![captura48](img/48.png)

Ara donem permisos d’execució a aquest script.
```
sudo chmod +x /root/fullbackup.sh
```
I el provem manualment
````
sudo /root/fullbackup.sh
````

![captura49](img/49.png)


Si no dóna errors, està bé.​

Ara programarem l'execució amb cron.
````
sudo crontab -e
````
````
I afegim aquesta línea al final:
````
0 23 * * 0 /root/fullbackup.sh
````
````
![captura50](img/50.png)

Desem els canvis amb
````
sudo crontab -l
````

![captura51](img/51.png)

Ara crearem un altre script que farà el mateix però fent una còpia incremental
````
sudo nano /root/incrementalbackup.sh
````
![captura52](img/52.png)



