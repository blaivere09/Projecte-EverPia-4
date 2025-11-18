# Fase 3: Treball en grup

## 1. Debat i Selecció
- Cada parella presenta el seu esquema. El grup debat els pros i contres de cada proposta (cost, temps de recuperació, seguretat, simplicitat).  
- Coincidències:
  - Prioritzar les dades més crítiques: **bases de dades, documents de projecte, carpetes personals**.  
  - No incloure còpia completa dels equips clients, només carpetes clau.  
- Comparació de propostes:
  - **Pol i Pau:** més fàcil d’implementar i administrar diàriament, recuperació ràpida per a la majoria d’incidents, cost assumible per una empresa petita.  
  - **Xavi/Blai:** periodicitat adaptada a RPO/RTO, opcions de còpia a llarg termini i diversificació de mitjans, més robustesa però amb major complexitat i cost.

---

## 2. Disseny de la Política Final
La **Política de Còpies de Seguretat Definitiva** per a l'empresa *Muntatges i Serveis Tècnics SL* és la següent:

- **Dades protegides:** documents de projectes, base de dades de Comptabilitat i Clients, carpetes personals dels usuaris.  
- **Periodicitat de còpies:**
  - **Comptabilitat i Clients:** còpies incrementals diàries + còpia completa setmanal.  
  - **Documentació i carpetes personals:** còpies diferencials diàries + còpia completa mensual.  
  - Retenció mínima: 1 mes.  
- **Mitjans i ubicació:**
  - **NAS** a l’oficina: recuperació ràpida de la informació.  
  - **Cloud:** còpia addicional fora de lloc per garantir recuperació en cas d’incident greu.  

> Aquesta política assegura la **disponibilitat i seguretat de les dades**, complint amb els requisits de l’empresa.


