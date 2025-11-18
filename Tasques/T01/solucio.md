# Fase 1: Treball individual

## a) FASE 1 POL

### Què copiarem?
- Bases de dades perquè són dades crítiques i usades diàriament.
- Documents de Projectes que contenen plànols i especificacions tècniques importants.
- Carpetes Documents dels Usuaris, ja que també poden contenir informació de treball important.

> No cal fer una còpia completa de tots els arxius personals dels Usuaris (equips clients), ja que podríem guardar molta informació innecessària com arxius temporals o personals. Com els Usuaris guarden la informació important dins de les carpetes **Documents**, només cal copiar aquestes.

### Cada quan i de quina manera?
- **Bases de dades:** còpies incrementals cada 4 hores (per complir RPO de 4 hores) i còpia completa setmanal.
- **Documents de Projectes i Carpetes Personals:** còpia diferencial diària i còpia completa setmanal.
- **Equips clients (carpetes Documents):** còpia incremental o sincronització diària.

### Quin mitjà usar i on guardar les dades
- **Mitjà local:** NAS (Network Attached Storage) per fer còpies ràpides i accessibles localment.
- **Mitjà extern:** còpia al núvol (Cloud) com Azure, Google Cloud o servei local, per garantir còpia fora de lloc.
- **Discs externs:** per a còpies mensuals/setmanals com SSD, HDD, cintes magnètiques.

**Regla 3-2-1:**  
3 còpies, 2 tipus de mitjans diferents (NAS + Cloud), i 1 còpia fora de lloc (Cloud).

---

## b) FASE 1 XAVI

### Dades a copiar (Priorització)
- **Bases de Dades (Comptabilitat i Clients, 20 GB):** dades crítiques, d’ús diari.
- **Documents de Projectes (300 GB):** importants per a l’activitat, amb creixement moderat i RPO de 24 h.
- **Carpetes Personals (100 GB):** necessàries per a la feina diària, menys crítiques que la BD.
- **Equips Clients (Windows 10/11):** només cal copiar els Documents locals, no tots els PCs.

### Periodicitat i Tipus de Còpia
- **Bases de Dades:** incremental cada 4 h, completa diària.
- **Documents de projectes:** incremental diària, completa setmanal.
- **Carpetes personals:** incremental diària, completa setmanal.

### Històric
- Retenció mínima d’1 mes → còpies setmanals/mensuals arxivades.

### Mitjans i Ubicació (Regla 3-2-1)
- NAS local per còpies ràpides i restauració immediata.
- Cloud per còpia externa.
- Discos externs per còpies setmanals/mensuals arxivades.

**Regla 3-2-1:**  
- 3 còpies de les dades (original + 2 còpies).  
- 2 tipus de mitjà diferents (NAS + Cloud).  
- 1 còpia fora de l’empresa (núvol o centre extern).  

> La còpia més recent ha d’estar en local (NAS) per a restauració ràpida, amb rèplica al Cloud per protegir contra desastres físics.

---

## c) FASE 1 BLAI

### Què copiarem?
- Bases de dades (registres de clients, factures)  
- Fitxers compartits (documents, projectes)  
- Configuració del servidor (comptes d’usuari, permisos)  
- Màquines virtuals (si n’hi ha)  
- Logs importants  

> No cal fer còpia de tots els ordinadors dels usuaris si les dades ja estan al servidor. Només cal copiar els ordinadors amb fitxers importants locals.

### Cada quan i de quina manera?
- **Cada dia laborable (dl-dv):** còpia incremental (només canvis des de l’última còpia).  
- **Setmanalment (ex. dissabte):** còpia diferencial (canvis des de l’última còpia completa).  
- **Mensualment:** còpia completa (totes les dades crítiques del servidor).

### Mitjans i Ubicació
- **Discs durs externs:** ràpids i fàcils d’utilitzar  
- **NAS:** centralitzat i accessible  
- **Cloud:** còpia fora de l’empresa  
- **Cintes:** per emmagatzemar grans volums durant molt de temps  

**Regla 3-2-1:**  
- Original al servidor  
- 1 còpia en mitjà diferent (NAS o disc extern)  
- 1 còpia fora del lloc (Cloud)

---

## d) FASE 1 PAU

### Què copiarem?
- Documents de projectes  
- Base de dades de Comptabilitat i Clients  
- Carpetes personals dels usuaris  

> Només cal copiar les carpetes amb fitxers importants temporalment; no tots els 10 equips clients.

### Cada quan i de quina manera?
- **Bases de dades:** còpia diària incremental  
- **Servidor complet:** còpia setmanal completa  
- **Documentació i carpetes personals:** còpia diària diferencial  
- **Totes les dades:** còpia mensual completa (per retenció mínima d’1 mes)

### Mitjans i Ubicació
- **NAS:** còpies ràpides i centralitzades (còpia més recent a l’oficina)  
- **Cloud:** còpia addicional per recuperar dades fora del lloc en cas d’incident greu

---

# Fase 2: Treball per parelles

## 1. Discussió i Consens
- Hem estat generalment d’acord en les dades que desitgem emmagatzemar.  
- Diferències principals sobre les carpetes dels usuaris:  
  - Resposta 1: només copia de la carpeta **Documents**.  
  - Resposta 2: còpia de **totes les carpetes personals**.  
- Totalment d’acord en **no emmagatzemar tots els fitxers** innecessaris, només els fitxers importants.  
- Diferències en la freqüència de còpies:  
  - Resposta 1: còpies més sovint.  
  - Resposta 2: còpies diàries però menys recurrents.  
- Tipus de còpia: consens complet.

---
[FASE 2 PARELLES](https://github.com/blaivere09/Projecte-EverPia-4/blob/main/Tasques/T01/FASE%202%20Treball%20en%20parelles.md)


