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

## 2. Elaboració d'una Proposta Unificada

Hem consensuat i dissenyat un **Esquema 3-2-1 de Còpies** basat en els requisits del cas (3 còpies, 2 mitjans, 1 fora de lloc).

| Element | Proposta de la Parella | Justificació |
|---------|----------------------|--------------|
| **Dades Crítiques** | Documents de projectes, BD de Comptabilitat i Clients, carpetes personals | Són les dades essencials per al funcionament diari |
| **Periodicitat (BD)** | Diària | Permet recuperar els canvis més recents sense perdre dades importants |
| **Tipus de Còpia (BD)** | Incremental diària, completa setmanal | Incremental diària per rapidesa i eficiència; completa setmanal per estabilitat |
| **Mitjà 1 (Local)** | NAS | Emmagatzema totes les còpies en un sol lloc, permet recuperació ràpida dins de l’oficina |
| **Mitjà 2 (Extern)** | Cloud | Assegura recuperació fora del lloc en cas d’incident greu, complint regla 3-2-1 |

---

# Fase 2: Treball per parelles

## 1. Discussió i Consens
Comparen les seves respostes individuals (Fase 1):

| Aspecte | Resposta (Xavi) | Resposta (Blai) | Coincidències / Diferències |
|---------|----------------|----------------|----------------------------|
| **Què copiar** | Bases de dades (prioritat màxima), documents de projectes, carpetes personals. No cal còpia completa dels 10 clients. | Bases de dades, documents, configuració del servidor, comptes d’usuari, permisos, màquines virtuals, logs. No cal còpia completa dels 10 clients. | Coincidim en no copiar tots els clients. Xavi es centra en dades d’ús diari; Blai afegeix configuracions i logs. |
| **Periodicitat** | BD: incremental cada 4 h + completa diària. Documents i carpetes: incremental diària + completa setmanal. | Incremental diària (dl-dv), diferencial setmanal (ds), completa mensual. | Diferència clara: Xavi proposa còpies molt freqüents per complir RPO de 4 h; Blai fa un esquema més genèric sense complir exactament el RPO. |
| **Tipus de còpia** | Combinació incremental + completa (BD i altres). | Incremental + diferencial + completa. | Xavi adapta al RPO/RTO; Blai aplica un esquema estàndard. |
| **Mitjans i ubicació** | NAS local + Cloud + discos externs (regla 3-2-1). | Discos externs + NAS + Cloud + cintes (regla 3-2-1). | Xavi aplica una solució moderna/pràctica; Blai afegeix cintes per llarg termini. |

---

## 2. Elaboració d'una Proposta Unificada
Disseny d’un **Esquema 3-2-1 de Còpies** basat en els requisits del cas (3 còpies, 2 mitjans, 1 fora de lloc):

| Element | Proposta de la Parella | Justificació |
|---------|----------------------|--------------|
| **Dades Crítiques** | Bases de dades de Comptabilitat i Clients, Documents de Projectes, Carpetes Personals | Són dades essencials per al funcionament diari. Les BD tenen requisits estrictes de RTO i RPO |
| **Periodicitat (BD)** | Còpia incremental cada 4 hores + còpia completa diària | Per garantir que no es perdin més de 4 hores de treball i que es pugui restaurar ràpidament |
| **Tipus de Còpia (BD)** | Incremental + Completa | Les incrementals són ràpides i eficients; les completes asseguren punts sòlids de restauració |
| **Mitjà 1 (Local)** | NAS local | Permet accés ràpid a les còpies i restauració immediata en cas d’error o pèrdua de dades |
| **Mitjà 2 (Extern)** | Cloud (còpia fora de l’empresa) | Protegeix contra desastres físics (incendis, robatoris) i garanteix la disponibilitat remota |

