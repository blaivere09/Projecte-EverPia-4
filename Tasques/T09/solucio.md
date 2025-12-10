# 🖥️ T09: Servidor de fitxers Linux  
## NFS (Tasca Individual)

---

## 🛠️ Fase 1: Configuració de l'entorn

Actualitzem les dues màquines:

sudo apt update -y && sudo apt upgrade -y

Comprovarem que les dues màquines es veuen entre si amb un IP:

```
ip a

```

![captura1](img/capt1.png)

![captura2](img/capt2.png)

---

## 👥 Creació de grups al servidor

Crearem dos grups: `devs` i `admins`:

```
sudo groupadd devs  
sudo groupadd admins

```
![caaptura3](img/capt3.png)

---

## 👤 Creació d'usuaris

Crearem dos usuaris i els assignarem als grups corresponents:

sudo useradd -m -G devs dev01  
sudo useradd -m -G admins admin01

![captura4](img/capt4.png)

---

## 📁 Creació de directoris

Crearem els directoris `admin_tools` i `dev_projectes`:



![captura5](img/capt5.png)

---

## 🔒 Assignació de permisos

El grup `devs` tindrà control total sobre els seus projectes, i el grup `admins` tindrà control total sobre les seves eines.  
L’usuari propietari serà `root` en tots dos casos.

![captura6](img/capt6.png)

---

## 🔍 Comprovació de permisos

Utilitzarem la següent comanda per comprovar els permisos:

```bash
ls -la /srv/nfs/

```
![captura7](img/capt7.png)

---

## ⚙️ Instal·lació del servei NFS

Instal·larem el servei NFS amb la següent comanda:

```bash
sudo apt install nfs-kernel-server

```

![captura8](img/capt8.png)

---

## ▶️ Habilitació i inici del servei NFS

Habilitarem i iniciarem el servei amb les següents comandes:

![captura9](img/capt9.png)

---

## 🖥️ Configuració al client

Ara, al client haurem de configurar els usuaris i grups amb les mateixes UID i GID.  
Per fer-ho, anotarem aquests identificadors del nostre servidor.

![captura10](img/capt10.png)

---

## ✅ Verificació

![captura11](img/capt11.png)

---

## ⚙️ Instal·lació del servei NFS al client

Ara instal·larem el servei necessari:

```bash
sudo apt install nfs-common -y

```

![captura12](img/capt12.png)
