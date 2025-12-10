# 📁💻 T09: Servidor de fitxers Linux amb NFS (tasca individual)

En aquesta tasca configurarem un **servidor de fitxers centralitzat** utilitzant NFS (Network File System) per a entorns Linux, d’acord amb les necessitats del client.

---

## 🌐 Context

**Client:** DevOptimize Solutions  
- Startup dedicada al desenvolupament de programari que utilitza exclusivament Linux.  
- Problema: els desenvolupadors treballen amb còpies locals del codi i actius, generant errors de versió i baixa eficiència.  
- Requisit: centralitzar les dades sense tenir un entorn d’autenticació centralitzat.

**Solució proposada:** **NFSv3**, ideal per entorns Linux sense LDAP o Kerberos.

---

## 🎯 Objectius de la tasca

- Configurar un **servidor NFS** i un **client Linux** que accedeixi als recursos compartits.  
- Simular usuaris i grups per demostrar el control d’accés.  
- Ajustar les opcions d’exportació en `/etc/exports` i permisos del sistema (`chmod`, `chown`).  
- Mostrar el funcionament de la solució i documentar possibles limitacions.

---

## 📂 Estructura de la tasca

A la carpeta `tasca09` trobareu:

- `activitat.md`: Guía i documentació pas a pas de la creació del servidor de fitxers Linux.

---

## 📎 Documents i referències

Tota la informació detallada i exemples addicionals es troben al repositori:  
[Projecte04-NFS](https://github.com/SMX2n/Projecte04-NFS)

