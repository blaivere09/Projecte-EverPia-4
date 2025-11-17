# T09: Servidor fitxers Linux. NFS (tasca individual)

## Breu descripció

### Introducció

Molt bé, equip de consultors júniors!  

En el nostre projecte, ens trobem amb un requisit tècnic molt habitual per part dels clients: **la centralització de dades en entorns Linux**.

---

### El Cas Client: DevOptimize Solutions

- **Client:** DevOptimize Solutions, una petita startup de desenvolupament de programari  
- **Problema:**  
  - Codi font i actius (documents de disseny, scripts) descontrolats  
  - Còpies locals de cada desenvolupador  
  - Errors de versió constants i pèrdua d’eficiència

- **Solució proposada:** Servidor de fitxers centralitzat  
  - Entorn: Linux  
  - Tecnologia: **NFS (Network File System, NFSv3)**  
  - Limitació: sense entorn d’autenticació centralitzada, segons demanda del client  

---

### Objectius de la Tasca

- Crear un **servidor NFS** i un **client Linux** que consumeixi els recursos compartits  
- Crear **usuaris i grups** per simular l’entorn del client  
- Demostrar el **control d’accés** amb:  
  - Opcions d’exportació (`/etc/exports`)  
  - Permisos del sistema de fitxers (`chmod`, `chown`)  
- Mostrar al client el funcionament i les limitacions de la solució

> En aquest repositori tens la descripció completa de la tasca:  
> [Projecte04-NFS](https://github.com/SMX2n/Projecte04-NFS)

---

## Materials i links de suport

- **Material propi:** UD5. AA1. NFS. Disponible al Moodle del mòdul de Sistemes Operatius en Xarxa  
- **Ruiz, P. (2021, novembre 22):** NFS (parte 1) – Instalación en un servidor Ubuntu 20.04 LTS  
  [Enllaç](https://somebooks.es/nfs-parte-1-instalacion-en-un-servidor-ubuntu-20-04-lts/)  
- **Ruiz, P. (2021, desembre 2):** NFS (parte 2) – Instalación en un cliente Ubuntu 20.04 LTS  
  [Enllaç](https://somebooks.es/nfs-parte-2-instalacion-en-un-cliente-ubuntu-20-04-lts/)  
- **Ubuntu Server Documentation – Network File System (NFS):**  
  [Enllaç](https://documentation.ubuntu.com/server/how-to/networking/install-nfs/)

