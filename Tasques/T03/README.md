# T03: Pla de recuperació davant desastres: imatges del sistema

## Breu descripció

### Introducció al cas
Recordeu el cas del portàtil al que no es podia accedir? En aquella situació, la vostra perícia tant a l’hora de recuperar l’accés com a la posterior fortificació de l’accés, va deixar prou impressionat al client.  

Ha encarregat l’elaboració d’un **Pla de Contingència i Continuïtat del Negoci**. Dins d’aquest pla, s’ha de posar en marxa el **Pla de Recuperació davant Desastres (DRP o Disaster Recovery Plan)**.  

Aquest pla inclou tots els processos de restauració de les dades, hardware i software crític de l’organització davant d’un esdeveniment catastròfic per tal de recuperar l’activitat normal el més ràpid possible.  

Un dels aspectes clau és assegurar que els treballadors puguin disposar de forma ràpida dels seus equips en cas de robatori, avaria, etc. Per aquest motiu, se’ns demana la creació d’**imatges de restauració del sistema**.  

El temps de posada en marxa és crític per l’àrea de negoci, per tant no és viable la solució clàssica d’instal·lar el sistema operatiu, aplicar configuracions i instal·lar aplicacions.  
Els equips del client són **GNU Linux**, concretament **Zorin OS 18**, amb una sèrie d’aplicacions ja configurades.

---

## Fase 1: Anàlisi i Justificació de la solució tècnica

En aquesta primera fase, caldrà investigar diverses eines que permetin:

- Crear una imatge del disc d’un equip.
- Restaurar-la posteriorment mantenint configuracions, aplicacions i dades originals.

El mercat ofereix moltes solucions, tant **comercials** com de **comunitat**.  

### Tasques:

1. Elaborar una **comparativa de productes**:
   - Trieu 2 de comercials i 2 de comunitat.
   - Incloure característiques destacades i preu.
   - Evitar copiar simplement informació de les webs dels productes.
2. Indicar quina seria la **solució proposada**, raonada i justificada segons la comparativa.

---

## Fase 2: Guia d'Ús Tècnica (Manual Operatiu)

A partir de la màquina proporcionada pel client (simulada amb una **OVA**):

### Procés a realitzar:

- Crear una **imatge completa del sistema**.
- Restaurar aquesta imatge sobre un sistema net (màquina virtual idèntica a l’original: RAM, CPU, xarxa, mida de disc), sense cap sistema operatiu instal·lat.
- Elaborar una **guia tècnica** que permeti al personal de manteniment realitzar ambdós processos.
- Incorporar **imatges significatives** per documentar el procediment.

> Com és una prova de concepte i encara no se sap si el client acceptarà la proposta, s’usarà **Rescuezilla** per a la guia.

**Aquesta tasca és individual.**

---

## Materials i links de suport

- **INCIBE:** ¿Ya tienes tu Plan de Recuperación ante Desastres? [Blog, Agost 2019](https://www.incibe.es/empresas/blog/tienes-tu-plan-recuperacion-desastres)  
- **Pàgina oficial de Rescuezilla:** [https://rescuezilla.com/](https://rescuezilla.com/)

