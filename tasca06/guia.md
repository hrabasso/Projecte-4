# T06: Accés remot — Windows ↔ Zorin (RDP/Remmina)

Guia breu per habilitar i provar l'accés remot entre un equip Windows i un equip Zorin OS.

---

## 1) Configuració a Windows (servidor RDP)

1. Configurem l'adaptador de xarxa en mode “només l'amfitrió”.

![Adaptador en mode host-only](./img/image1.png)

---

2. Obrim la configuració d'“Escritorio remoto”.

![Accés a configuració d'escriptori remot](./img/image2.png)

---

3. Activem l'escriptori remot.

![Activar RDP](./img/image3.png)

---

## 2) Configuració a Zorin (servidor VNC/RDP)

1. A Zorin, anem a Settings → System → Remote Desktop.

![Remote Desktop a Zorin](./img/image4.png)

---

2. Activem “Desktop sharing” i “Remote control”; definim usuari i contrasenya de l'usuari actiu.

![Activar desktop sharing i control remot](./img/image5.png)

---

## 3) Connexió des de Windows cap a Zorin

1. Obrim l'aplicació “Conexión a Escritorio Remoto” a Windows i introduïm la IP de Zorin (obtinguda amb `ip a`).

![IP de Zorin](./img/image6.png)


---

2. Introduïm usuari i contrasenya quan es demani.

![Credencials de Zorin](./img/image7.png)

---

3. Acceptem l'avís del certificat.

![Avís de certificat](./img/image8.png)

---

4. Sessió remota establerta.

![Sessió Zorin des de Windows](./img/image9.png)

---

## 4) Connexió des de Zorin cap a Windows (Remmina)

1. A Zorin, obrim Remmina (client de connexions remotes per defecte) i creem una connexió.

![Remmina a Zorin](./img/image10.png)

---

2. Acceptem també l'avís de certificat.

![Certificat en Remmina](./img/image11.png)

---

3. Introduïm usuari i contrasenya i accedim.

![Sessió Windows des de Zorin](./img/image12.png)

---

Fi.
