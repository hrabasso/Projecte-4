# T02: DPR — Còpies de seguretat. Cas pràctic
---

## Part 1 — Còpia de seguretat en Windows amb Duplicati

**Objectiu:**  
Realitzar còpies de seguretat del perfil d’usuari:
- Còpies **horàries** a un disc secundari local.
- Còpia **diària a les 18:00** cap a **Google Drive**.

---

### Instal·lació del sistema i preparació

Durant la instal·lació de Windows es crea una partició secundària que s’utilitzarà exclusivament per a les còpies locals.

(./img/img4.jpg)

Instal·lació del sistema operatiu Windows 11.
(./img/img9.jpg)

Un cop finalitzada la configuració inicial, s’instal·la Google Chrome per facilitar l’accés a serveis web com Google Drive.

(./img/img10.jpg)

---

### Instal·lació i configuració de Duplicati

Es descarrega Duplicati des del lloc oficial i s’instal·la al sistema.

(./img/img13.jpg)
(./img/img14.jpg)

Un cop instal·lat, accedim a la interfície web de Duplicati.

(./img/img17.jpg)

Creem una nova tasca de còpia de seguretat.

![Crear feina](./img/img18.jpg)

Seleccionem **New backup**, ja que no disposem de cap configuració prèvia.

(./img/img21.jpg)

Configurem una contrasenya per xifrar les còpies.

(./img/img24.jpg)

Seleccionem com a destinació el disc secundari (D:).

(./img/img25.jpg)

Escollim les carpetes del perfil d’usuari que es volen protegir (Documents).
(./img/img28.jpg)

Definim una planificació **horària** per a la còpia local.

(./img/img32.jpg)

Revisem el resum de la configuració i guardem la tasca.

(./img/img33.jpg)

---

### Còpia de seguretat a Google Drive

Es crea una segona tasca similar, però seleccionant **Google Drive** com a destinació.

Durant el procés, Duplicati sol·licita un **AuthID** per autoritzar l’accés al compte de Google.

(./img/img37.jpg)

Accedim a l’enllaç indicat, iniciem sessió amb Google i obtenim el codi d’autorització.

(./img/img38.jpg)

Introduïm el codi a Duplicati per completar la vinculació.

(./img/img41.jpg)

Finalment, configurem la còpia perquè s’executi **diàriament a les 18:00**.

(./img/img47.jpg)

---

### Verificació i restauració

Creem un fitxer de prova dins de Documents.

(./img/img50.png)

Executem manualment la còpia de seguretat.

(./img/img53.jpg)

Esborrem el fitxer original.

(./img/img54.jpg)

Restauració del fitxer mitjançant Duplicati.

(./img/img60.jpg)
(./img/img71.jpg)
(./img/img74.jpg)

---

## Part 2 — Còpia de seguretat en Linux amb Duplicity

**Objectiu:**  
Realitzar còpies completes i incrementals del directori `/home` cap a una unitat auxiliar muntada manualment a `/media/backup`.

---

### Preparació del disc de backup

Es detecta el disc auxiliar, es formateja amb sistema de fitxers **XFS** i es crea el punt de muntatge.

(./img/img80.jpg)
(./img/img81.jpg)

Es munta manualment la unitat.

(./img/img82.jpg)
(./img/img85.jpg)

---

### Preparació de l’entorn

Es creen usuaris addicionals per generar dades de prova.

(./img/img89.jpg)

Instal·lació de Duplicity al sistema Linux.

(./img/img86.jpg)

Creació de fitxers de prova dins dels directoris `/home`.

(./img/img92.jpg)

---

### Còpies completes i restauració

Execució d’una còpia completa del directori `/home`.

(./img/img93.jpg)
(./img/img96.jpg)

Simulem una pèrdua de dades i restaurem el contingut.

(./img/img97.jpg)
(./img/img100.jpg)

---

### Còpies incrementals

Afegim un nou fitxer d’uns 4 MB.
(./img/img101.jpg)

Executem una còpia incremental i comprovem les versions.

(./img/img102.jpg)
(./img/img105.jpg)

---

### Automatització amb cron

Desmuntem la unitat de backup per seguretat.

(./img/img106.jpg)

Creem scripts de còpia i assignem permisos d’execució.

(./img/img109.jpg)
(./img/img110.jpg)

Configurem les tasques programades amb **cron**.
(./img/img111.jpg)
(./img/img121.jpg)
