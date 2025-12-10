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
![captura3](capt3.png)
