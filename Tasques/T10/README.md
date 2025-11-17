# T10: Servidor impressió Linux. CUPS (tasca individual)

## Breu descripció

### Introducció

Molt bé, equip!  

A EverPia busquem **optimitzar els recursos dels clients** per reduir costos i simplificar la gestió.  
Un dels punts més caòtics en qualsevol oficina és la **gestió d'impressores**:  

- Drivers incompatibles  
- Costos de tòner descontrolats  
- Equips que no saben a quina impressora enviar la feina  

La solució professional és implementar un **Servidor d'Impressió Centralitzat**.  

El client **DevOptimize Solutions** vol centralitzar la impressió a tots els seus departaments amb:  

- Clients Linux (Zorin OS)  
- Servidors Ubuntu Server  

---

## La Vostra Missió: Prova de Concepte (PoC)

Abans de comprar impressores de xarxa cares, el client vol veure una **PoC** que demostri que un servidor Linux pot gestionar una impressora i compartir-la amb els clients Zorin.  

- Per simular la impressora, s’utilitzarà **cups-pdf**, que genera fitxers PDF en lloc d’imprimir en paper.  
- L’objectiu és configurar aquest escenari i demostrar que el client pot enviar treballs d’impressió al servidor.  

---

## Escenari de Treball

- Màquina 1 (Servidor): Ubuntu Server amb NAT + Host-Only  
- Màquina 2 (Client): Zorin OS amb la mateixa configuració de xarxa que el servidor  

> Es recomana seguir l’escenari de la PoC de NFS i reutilitzar les mateixes màquines.

---

## PoC (Prova de concepte)

1. Instal·lació de **CUPS** al servidor  
2. Instal·lació de la **impressora virtual cups-pdf**  
3. Configuració de l’administració de CUPS i permetre que **CUPS escolti per totes les interfícies**  
4. Compartir la impressora des del **frontal web de CUPS**  
5. Afegir la impressora al client Zorin  
6. Fer una prova d’impressió de diversos documents  
7. Comprovar al servidor que s’han generat els fitxers PDF corresponents  

> Documenteu les comandes utilitzades i afegiu **captures de pantalla** per demostrar el correcte funcionament.

---

## Materials i links de suport

- **Material propi:** UD5. AA1. CUPS – Disponible al Moodle del mòdul de Sistemes Operatius en Xarxa  
- **Vídeo:** J.B. Alex Mantich (2024, 15 febrer). Instalació de servidor d’impressió en CUPS per Linux  
  [YouTube](https://www.youtube.com/watch?v=FNwSTrOSgZQ)  
- **Documentació Ubuntu:** Network File System (NFS) – [Ubuntu Server Documentation](https://documentation.ubuntu.com/server/how-to/networking/install-nfs/)  
- **Tutorial Idroot:** How To Install CUPS Print Server on Ubuntu 24.04 LTS (R00t/2025, 25 abril)  
  [Enllaç](https://idroot.us/install-cups-print-server-ubuntu-24-04/)

