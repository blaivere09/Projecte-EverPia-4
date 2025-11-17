# T02: DPR: còpies de seguretat. Cas pràctic

## Breu descripció

### Introducció al cas
A la tasca anterior heu dissenyat una política de còpies de seguretat pel nostre nou client **"Muntatges i Serveis Tècnics SL"**. Ara toca passar a l’acció i portar a la pràctica l’estudi anterior. El client demana que s’elaborin unes guies tècniques amb proves de concepte per tal que el seu personal estigui qualificat per implantar el pla de còpies de seguretat.

---

## Part 1: Còpia de seguretat dels equips clients Windows

Encara que en principi el DPR no contemplaria fer còpia dels arxius locals dels equips clients, se’ns demana fer una excepció amb l’equip Windows del director de l’empresa.  
En aquest equip es guarda informació important que no es vol tenir accessible al servidor de fitxers de l’empresa. Per aquest motiu:

- Es necessari definir una política de còpies de seguretat seguint l’esquema **3-2-1**.
- Es farà una còpia de seguretat a un disc secundari que té el propi equip.
- Una segona còpia es farà al **cloud**, en aquest cas Google Drive, usant l’eina **Duplicati**.

### Procediment de prova de concepte

1. Creeu una màquina virtual Windows 11 amb dos discos:
   - Disc 1: Sistema operatiu.
   - Disc 2: Secundari de 10 GB per emmagatzemar les còpies.
2. Per simular Google Drive, useu un compte que no sigui el d’escola.
3. Configureu les còpies de seguretat del perfil de l’usuari:
   - Cada hora al disc secundari.
   - A les 18:00 a Google Drive.
4. Documenteu el procediment:
   - Instal·lació de Duplicati.
   - Configuració dels plans de còpies.
   - Afegiu arxius a les carpetes de l’usuari (especialment a **Documents**).
5. Esborreu el contingut de **Documents** i feu una restauració des del disc secundari.
6. Comproveu la restauració des del cloud.

---

## Part 2: Còpia de seguretat del servidor Linux

Per fer les còpies del servidor Linux la solució proposada és **Duplicity**, que permet fer còpies tant contra un mitjà local com un servidor remot.  
Combinat amb el programador de tasques (**cron**) es poden implementar les polítiques de còpia desitjades.

### Guia tècnica i prova de concepte

1. Creeu una màquina virtual amb Ubuntu Server i un segon disc de 10 GB que simuli una unitat auxiliar:
   1. Inicialitzeu i formateu en format **xfs**.
   2. Munteu la unitat manualment a `/media/backup` (crear carpeta si cal).
2. Instal·leu **Duplicity**.
3. Creeu un parell d’usuaris nous amb carpetes personals.  
   Crea 4 arxius de 10 MB a la carpeta home del vostre usuari.
4. Feu una còpia de seguretat de la carpeta `/home`.
5. Esborreu els arxius i realitzeu un restore per comprovar la recuperació.
6. Afegiu un nou arxiu de 4 MB i feu una nova còpia per observar la còpia **incremental**.
7. Desmunteu la unitat de backup.

### Automatització amb scripts i cron

- La unitat de backup ha d’estar **per defecte desmuntada**.  
  Els scripts han de muntar la unitat al començament i desmuntar-la al final.

1. Creeu un script `fullbackup.sh` que:
   - Realitzi la còpia completa de `/home`.
   - Emmagatzemi les dades al volum muntat.
   - Utilitzi la variable d’entorn `PASSPHRASE` per evitar introduir-la manualment.
   - Donar permisos d’execució.
2. Programeu el cron com a root per executar `fullbackup.sh` els diumenges a les 23:00.
3. Creeu un segon script `incrementalbackup.sh` per còpies incrementals de `/home`.
   - Fixeu la variable `PASSPHRASE` igual que en el primer script.
   - Doneu permisos d’execució.
4. Programeu el cron per executar `incrementalbackup.sh` de dilluns a dissabte a les 23:00.

---

## Materials i links de suport

- **Duplicati:** [https://duplicati.com/](https://duplicati.com/)  
- **WayToIT. Creando archivos con fsutil [blog], març 2015:** [https://waytoit.wordpress.com/2015/03/15/creando-archivos-con-fsutil/](https://waytoit.wordpress.com/2015/03/15/creando-archivos-con-fsutil/)  
- **WayToIT. Creando archivos de prueba en Linux [blog], març 2015:** [https://waytoit.wordpress.com/2015/03/21/creando-archivos-de-prueba-en-linux/](https://waytoit.wordpress.com/2015/03/21/creando-archivos-de-prueba-en-linux/)  
- **Duplicity man page:** [http://manpages.ubuntu.com/manpages/trusty/man1/duplicity.1.html](http://manpages.ubuntu.com/manpages/trusty/man1/duplicity.1.html)  
- **Programant tasques amb cron:** [https://geekytheory.com/programar-tareas-en-linux-usando-crontab](https://geekytheory.com/programar-tareas-en-linux-usando-crontab)

