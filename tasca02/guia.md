
# T02: DPR — Còpies de seguretat. Cas pràctic

Guia tècnica amb proves de concepte per implantar el pla de còpies de seguretat per al client "Muntatges i Serveis Tècnics SL". S'aplica l'esquema 3-2-1 i es documenten els procediments de Windows (Duplicati) i Linux (Duplicity + cron).

---

## Part 1 — Còpia de seguretat en Windows amb Duplicati (perfil d'usuari)

Objectiu: còpies horàries del perfil d'usuari a un disc secundari i còpia diària a les 18:00 cap a Google Drive, mostrant el procés amb captures.

### Seqüència d'instal·lació i configuració

Creació de partició en el moment d'instal·lar Windows.

![Partició durant instal·lació](./img/img4.jpg)

---

Instal·lació de Windows 11.

![Instal·lació Windows](./img/img9.jpg)

---
Assistim la instal·lació fins completar la configuració inicial de l'equip.

Instal·lació de Google Chrome.

![Instal·lació Chrome](./img/img10.jpg)

---
Instal·lem el navegador per facilitar l'accés a serveis com Google Drive.

Instal·lació i configuració de Duplicati: creació de treball, selecció de destí local (disc secundari de 10 GB), selecció de carpetes (Documents), planificació horària i opcions.

![Descarregar duplicaty](./img/img13.jpg)
Descarrega de l’instal·lador de Duplicati des del lloc oficial.

---

![Instal·lació duplicatty](./img/img14.jpg)
Procés d’instal·lació de Duplicati a Windows.

---

![Pantalla inicial Duplicati](./img/img17.jpg)
Vista d’inici de l’aplicació, punt de partida per crear un backup.

---

![Crear feina](./img/img18.jpg)
Creació d’un nou treball de còpia de seguretat.

---

![New backup](./img/img21.jpg)
Seleccionem new backup perque no tenim res per importar .

---

![Creem password](./img/img24.jpg)
Posem una password que ens enrecordem

---

![Posem la carpeta desti](./img/img25.jpg)
Posem que es guardin a el disc D:

---

![Seleccionar carpetes](./img/img28.jpg)
Selecció de les carpetes del perfil que es volen copiar (Documents, etc.).

---

![Programació cada hora](./img/img32.jpg)
Definició de la periodicitat horària per a les còpies locals.

---

![Resum tasca](./img/img33.jpg)
Resum final de la configuració abans de guardar i executar.

---

# Creem la copia a google drive

## Es lo mateix pero loguejant-nos amb google drive

---

![Resum tasca](./img/img36.jpg)
Ens demana un AuthID i no el tenim, tot i aixi continuem endevant.

---

![Resum tasca](./img/img37.jpg)

Ara en surt aquest error i entrem al link.

---

![Resum tasca](./img/img38.jpg)
Entrem i ens logueijem i ens donara aquest codi.

---

![Resum tasca](./img/img41.jpg)

Ara posem el codi on ens demanaba AuthID.

---
![Resum tasca](./img/img47.jpg)

Seguim els mateixos pasos d'abans pero cambiant la hora i dia i ja tendriem les copies creades.

---
# Comprobvació

Crear un fitxer de prova a Documents.

![Fitxer de prova](./img/img50.png)

---
Afegim un fitxer per comprovar que la còpia captura correctament els canvis.

Executar la còpia de seguretat a Duplicati.

![Execució backup](./img/img53.jpg)

---

Esborrar el fitxer a Documents.

![Esborrar Documents](./img/img54.jpg)

---

---

Recuperar el document.

![Esborrar Documents](./img/img60.jpg)
![Esborrar Documents](./img/img71.jpg)
![Esborrar Documents](./img/img74.jpg)

---

---

## Part 2 — Còpia de seguretat a Linux amb Duplicity + cron

Objectiu: implementar còpies completes i incrementals de `/home` en un volum auxiliar muntat manualment a `/media/backup`, mostrant-ho amb captures i sense comandos en el text.

### Seqüència de la prova de concepte

Preparació de la unitat de backup (10 GB): detectar el disc, formatejar en XFS, crear punt de muntatge.

![Formatar XFS](./img/img80.jpg)
![Crear punt de muntatge](./img/img81.jpg)

---
Es defineix el sistema de fitxers i el punt de muntatge per a la unitat auxiliar.

Muntatge manual a `/media/backup`.

![Muntar volum](./img/img82.jpg)
![Volum muntat](./img/img85.jpg)

---
Crear usuaris.

![Muntar volum](./img/img89.jpg)

---

El volum queda disponible per rebre còpies de seguretat.

Instal·lació de Duplicity.

![Instal·lar duplicity](./img/img86.jpg)

---
Instal·lació de l'eina de còpia per entorns Linux.

Preparar dades de prova: crear usuaris addicionals i fitxers de 10 MB en `home`.

![Crear fitxers de prova](./img/img92.jpg)

---
Creem usuaris i contingut per validar les còpies.

Fer una còpia completa de `/home` cap a la unitat de backup.

![Backup complet /home](./img/img93.jpg)
![Verificar contingut backup](./img/img96.jpg)

---

Verificar restauració: esborrar i restaurar fitxers.

![Esborrar fitxers](./img/img97.jpg)
![Restore complet](./img/img100.jpg)

---
Es simula una pèrdua de dades i es verifica la recuperació.

Fer una còpia incremental després d'afegir un fitxer de ~4 MB.

![Crear nou fitxer](./img/img101.jpg)
![Backup incremental](./img/img102.jpg)
![Comprovació versions](./img/img105.jpg)

---
Es genera un canvi menor i s'executa una còpia incremental per observar diferències.

Desmuntar la unitat de backup.

![Desmuntar](./img/img106.jpg)

---
La unitat queda desconnectada per seguretat.

Automatització amb scripts i cron (captures del procés).

---

Creem els scripts i donem permisos
![Permisos execució](./img/img109.jpg)
![Permisos execució](./img/img110.jpg)
![Permisos execució](./img/img117.jpg)
![Permisos execució](./img/img118.jpg)

Obrim el arxiu de crontab per posar las tascas que volem que cron executi
![Permisos execució](./img/img111.jpg)
![Cron incremental](./img/img121.jpg)

---

## Notes i bones pràctiques

- Mantén la passphrase fora de scripts si pots (usa variables d'entorn o fitxers protegits).
- Verifica periòdicament les restauracions (no n'hi ha prou amb fer còpies, cal provar retorn).
- Aplica la regla 3-2-1: producció + 2 còpies, en 2 suports diferents, amb 1 còpia off-site.
- Documenta la configuració i versions instal·lades.

---

## Materials i enllaços

- Duplicati: https://www.duplicati.com/
- Duplicity: https://duplicity.us/

´
