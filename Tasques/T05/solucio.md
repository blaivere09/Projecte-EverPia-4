# T05: Accés remot 💻

Haurem de tenir **dues VM**, amb **dues interfícies de xarxa** cadascuna:  
- NAT  
- Host-Only  

Per tant, **DHCP activat** (`true`).  

A continuació, instal·larem **SSH**:

```bash
sudo apt upgrade && sudo apt update && sudo apt install ssh -y

```
![captura1](img/capt1.png)

![captura2](img/capt2.png)

---

També habilitarem i iniciarem el servei **SSH**:

```bash
sudo systemctl enable ssh
sudo systemctl start ssh

```

sudo systemctl status ssh

![captura3](img/capt3.png)

---

Un cop hem identificat la **IP del nostre servidor**, haurem d’instal·lar i configurar un **client Windows**.  

Després, accedirem al terminal **PowerShell** i, des d’allà, ens podrem connectar al servidor mitjançant **SSH**:

```powershell
ssh usuari@[ip]

```

![captura4](img/capt4.png)

---

Si volem **desactivar l’ús de l’usuari root** en connexions SSH per garantir una major seguretat, haurem d’editar el fitxer:

```bash
/etc/ssh/sshd_config
```

![captura5](img/capt5.png)

![captura6](img/capt6.png)

---

Fent això, indiquem que el **port de connexió** és el **20** (`Port 20`) i que no es permetin connexions com a **root** (`PermitRootLogin prohibit-password`).

![captura7](img/capt7.png)

---

Per fer comprovació, crearem un **nou usuari** (`usuari2`) i provarem de connectar-nos per SSH amb aquest:

```bash
sudo adduser usuari2
ssh usuari2@192.168.56.101
```

![captura8](img/capt8.png)

---

Com podem veure, tenim **accés denegat**. ❌

Ara tot el trànsit del client s’envia com si fos el servidor, però si volem afegir una **redirecció dinàmica** (dynamic forwarding), ens hem de connectar amb una variació de la comanda:

```bash
ssh -D 9876 usuari@192.168.56.101
```

![captura9](img/capt9.png)

---

Ara configurarem el **túnel de SOCKS** 🧦

| Imatge 1 | Imatge 2 | Imatge 3 |
|----------|----------|----------|
| ![captura10](img/capt10.png) | ![captura11](img/capt11.png) | ![captura12](img/capt12.png) |

---

Amb Wireshark podem comprovar que tot el trànsit que generem s’envia per **SSH** al servidor. Podem veure les comunicacions entre `127.0.2.7` (IP del client) i `192.168.56.101` (IP del servidor).

![captura13](img/capt13.png)

---

Seguint el vídeo de **Carlos Alonso**.

![captura14](img/capt14.png)

![captura15](img/capt15.png)

![captura16](img/capt16.png)

![captura17](img/capt17.png)


