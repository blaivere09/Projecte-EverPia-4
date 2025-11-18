# Document Final (Fase 3)

El grup ha de generar un document amb els següents punts resolts:

---

## 1) Dades Objecte de Còpia

### Servidor

| Tipus de Dada                  | Crítica | Freqüència de Còpia                           |
|--------------------------------|---------|-----------------------------------------------|
| Bases de Dades (Comptabilitat/Clients) | ✅      | Incremental cada 4 h + completa diària       |
| Documents de Projectes          | ✅      | Incremental diària + completa setmanal       |
| Carpetes Personals dels Usuaris | ❌      | Incremental diària + completa setmanal       |

### Equips dels Clients

| Tipus de Dada                  | Crítica | Freqüència de Còpia                                      |
|--------------------------------|---------|----------------------------------------------------------|
| Documents locals temporals      | ❌      | No es copia (es recomana guardar al servidor)           |
| Configuracions especials        | ✅ (si n’hi ha) | Còpia puntual si són difícils de recuperar        |

### Quines dades es copien i amb quina freqüència

#### Servidor

- **Dades crítiques:** Base de dades de Comptabilitat i Clients, documents de projectes → còpia incremental diària, còpia completa setmanal, còpia mensual completa.
- **Dades no crítiques:** Carpetes personals dels usuaris → còpia diferencial diària, còpia mensual completa.

#### Clients

- **Dades crítiques:** Només les carpetes clau dels tècnics → còpia diferencial diària, còpia mensual completa.
- **Dades no crítiques:** La resta dels fitxers dels equips clients no es copien, ja que la informació important està centralitzada al servidor.

---

## 2) Cronograma Setmanal Detallat

| Dia       | Dades (Ex: BD)                          | Tipus de còpia | Mitjà |
|-----------|-----------------------------------------|----------------|-------|
| Dilluns   | Comptabilitat/Clients, documents de projectes | Incremental    | NAS   |
|           | Carpetes personals dels usuaris         | Diferencial    | NAS   |
| Dimarts   | Comptabilitat/Clients, documents de projectes | Incremental    | NAS   |
|           | Carpetes personals dels usuaris         | Diferencial    | NAS   |
| Dimecres  | Comptabilitat/Clients, documents de projectes | Incremental    | NAS   |
|           | Carpetes personals dels usuaris         | Diferencial    | NAS   |
| Dijous    | Comptabilitat/Clients, documents de projectes | Incremental    | NAS   |
|           | Carpetes personals dels usuaris         | Diferencial    | NAS   |
| Divendres | Comptabilitat/Clients, documents de projectes | Incremental    | NAS   |
|           | Carpetes personals dels usuaris         | Diferencial    | NAS   |
| Dissabte  | Comptabilitat/Clients, documents de projectes | Incremental    | NAS   |
|           | Carpetes personals dels usuaris         | Diferencial    | NAS   |
| Diumenge  | Còpia completa de tot el servidor i dades clients | Completa       | NAS + Cloud |

---

## 3) Elecció de Mitjans i Ubicació (Regla 3-2-1)

- **Mitjà 1 (Local):** NAS ubicat a l’oficina, que emmagatzema totes les còpies de manera centralitzada i permet una recuperació ràpida de la informació.  
- **Mitjà 2 (Extern):** Cloud, utilitzant un servei segur com Microsoft Azure o Google Cloud, per garantir còpia fora del lloc i alta disponibilitat.  
- **Ubicació Fora de Lloc:** La còpia externa es guarda al Cloud, gestionada pel proveïdor del servei i supervisada pel responsable de sistemes de l’empresa per assegurar accessibilitat i seguretat en cas d’incident.

---

## 4) Estratègia de Recuperació (RTO/RPO)

Per garantir que les dades de Comptabilitat i Clients compleixen amb un **RPO de 4 hores**, es realitzen còpies incrementals diàries que capturen els canvis més recents i minimitzen la pèrdua de dades.

Per assolir un **RTO de 4 hores**, la recuperació es fa des del NAS local per obtenir accés immediat, amb la còpia al Cloud com a alternativa en cas que el servidor local no estigui disponible. Això garanteix que les dades es puguin recuperar ràpidament i que els problemes afectin poc el funcionament de l’empresa.

---
fet per Blai Vergés, Pol Valles, Xavier Lopez i Pau Guerrero
