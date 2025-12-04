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
