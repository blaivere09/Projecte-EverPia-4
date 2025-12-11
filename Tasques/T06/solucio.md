# T06: Accés remot - Escriptori remot (RDP)

Per realitzar aquesta pràctica necessitarem **dues màquines virtuals**: una amb Windows i una altra amb Zorin. Ambdues han d’estar configurades amb **xarxa NAT** perquè puguin comunicar-se entre elles dins la mateixa xarxa.

Abans de començar, farem **comprovacions inicials** utilitzant `ping`. Tingues en compte que cal **desactivar el firewall de Windows**, si no, la connexió no funcionarà correctament!


![captura1](img/capt1.png)

![captura2](img/capt2.png)

---

Com a primer pas, cal disposar d’una **màquina virtual amb Windows** i habilitar l’**escriptori remot**.  
Això es fa des de **Configuració → Sistema → Escriptori remot**.

![captura3](img/capt3.png)

---

A més, podrem **afegir usuaris d’escriptori remot**.

**IMPORTANT:** Cal crear un **nou usuari** per poder connectar-nos si no en tenim cap.  
Es pot fer des de:  
**Configuració → Comptes → Afegir un nou compte → Sense un compte de Microsoft**  
i seguir les instruccions que apareixen.


![captura4](img/capt4.png)

---


Ara haurem d’entrar a la **segona VM**, una màquina amb Zorin.  
Provarem de connectar-nos a l’escriptori remot de Windows; per fer-ho, hem d’obrir **Remmina**.

![captura5](img/capt5.png)



![captura6](img/capt6.png)



![captura7](img/capt7.png)

---


Ara activarem el **control remot** a Zorin.  

1. Accedeix a **Configuració → Compartir**.  
2. Activa **"Compartir pantalla"**.  
3. Activa **"Control remot"** i defineix una **contrasenya**.  

Després, estableix les dades d’accés segons sigui necessari.

![captura8](img/capt8.png)

---
Des de **Windows**, ara podem connectar-nos a **Zorin** mitjançant l’**Escriptori remot**.  
Obrim l’aplicació i introduïm les **dades d’accés**.

![captura9](img/capt9.png)

---

- **Equip:** `usuari-VirtualBox.local`, tal com vam observar abans quan vam configurar l’escriptori remot a Zorin.  
- **Usuari:** `usuari`, ja que és el que vam definir a Zorin.

![captura10](img/capt10.png)

---

Introduïm la contrasenya que hem definit a la configuració a zorin.

![captura11](img/capt11.png)

---

Acceptem i ja hem entrat dins

![captura12](img/capt12.png)

---

**fet per blai vergés*
