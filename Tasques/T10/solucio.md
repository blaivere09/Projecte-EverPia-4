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

