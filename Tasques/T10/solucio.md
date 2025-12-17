# T10: Servidor impressió Linux. CUPS (tasca individual)

Maquina 1 (servidor) Ubuntu server.

En primer lloc he posat el adaptador de xarxa en NAT i el 2n en adaptador ANFITRIÓ.

[capt1](img/1.png)

[capt2](img/2.png)

Farem el maiteix amb la maquina de CLIENT.

[capt3](img/3.png)

[capt4](img/4.png)

 Instal·lació de CUPS al servidor

Abans d'instal·lar **CUPS**, primer actualitzem el sistema per assegurar-nos que tots els paquets estan al dia. Executem la següent comanda:

```bash
sudo apt update -y && sudo apt upgrade -y
```

[capt5](img/5.png)

```
````
Un cop finalitzat el procés d'actualització, ja podem instal·lar **CUPS** amb la següent comanda:

```bash
sudo apt install cups -y
```

[capt6](img/6.png)


Instal·lar impressora virtual

Per instal·lar la nostra impressora virtual, entrem com a **root** al nostre client amb la comanda:

```bash
sudo su
```

Un cop som root, instal·lem la impressora virtual amb:

```bash
apt install cups-pdf
```
[capt7](img/7.png)


Configuració de l’administració de CUPS i permetre que CUPS escolti per totes les interfícies

Abans de modificar l’arxiu de configuració, és recomanable fer-ne una còpia de seguretat.

Per editar l’arxiu, utilitzem la comanda:

```bash
sudo nano /etc/cups/cupsd.conf
```

Un cop dins, cal canviar aquestes dues línies:

```bash
Listen localhost:631 → Port 631
Browsing No → Browsing On
```

[capt8](img/8.png)




A més, cal permetre l’accés des de la xarxa local al servidor web de gestió. Afegim o modifiquem les següents seccions dins del fitxer:

```bash
<Location
```

[capt9](img/9.png)

Aqui es pot veure com ja he cambiat manualment la configuració.


Reinici del servei de CUPS

Un cop modificat el fitxer de configuració, reiniciem el servei de CUPS i comprovem que funcioni correctament:

```bash
systemctl restart cups && systemctl status cups
```

[capt10](img/10.png)


4. Usant el navegador i el frontal web de CUPS per compartir la impressora

Un cop el servei estigui funcionant, hem d’obrir el navegador i introduir la següent adreça a la barra de cerca:

```bash
https://10.0.2.15:631
```

Explicació:

* `10.0.2.15` → La IP del nostre adaptador de xarxa `enp0s3`
* `631` → El port que hem configurat anteriorment

> Si apareix un avís que indica que el lloc no és segur, cal seleccionar **Avanzado** i després **Acceder a 10.0.2.15 (sitio no seguro)**

[capt11](img/11.png)


## 5. Afegir la impressora al client Zorin

Per afegir la impressora, cal obrir **Administración**, que es troba a la barra superior d’opcions.

Si apareix de nou la pàgina d’advertència de lloc no segur, fem el mateix procediment anterior, però aquesta vegada haurem d’iniciar sessió amb les credencials del nostre client.

[capt12](img/12.png)

Un cop dins, seleccionarem l’opció de afegir una impresora

[capt13](img/13.png)


Quan accedim, no es deixara fer res per falta de permisos

[capt14](img/14.png)
