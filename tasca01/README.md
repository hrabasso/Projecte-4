# T01: DRP: Còpies de Seguretat - Estudi de Cas Client

## Fase 1: Anàlisi Individual

1. **Dades Crítiques**
   - Bases de dades de comptabilitat i clients: canvien constantment, RPO de 4 hores.
   - Documents de projectes.
   - Carpetes personals dels tècnics (només la carpeta “Documents”, la resta ja està al servidor).

2. **Periodicitat de Còpies**
   - Bases de dades: còpia completa cada nit i incrementals cada 4 hores.
   - Projectes i carpetes personals: còpia completa setmanal i diferencial diària.
   - Equips clients: còpia completa setmanal i incremental al final del dia.

3. **Mitjans**
   - NAS intern per a còpies diàries ràpides.
   - Discs externs xifrats per a còpies setmanals.
   - Servei de cloud per a còpies mensuals.
   - Regla 3-2-1: còpies en dos suports diferents i una fora de l’empresa.

---

## Fase 2: Treball per Parelles

### Treballant per parelles

1. **Discussió i Consens**
   - Comparació de les respostes individuals (Fase 1).

2. **Elaboració d'una Proposta Unificada**
   - Disseny de l’Esquema 3-2-1 de Còpies (3 còpies, 2 mitjans, 1 fora de lloc) basat en els requisits del cas.

| Element              | Proposta de la Parella                                            | Justificació                                                                 |
|---------------------|------------------------------------------------------------------|----------------------------------------------------------------------------|
| **Dades Crítiques**  | Bases de dades de Comptabilitat/Clients, documents de Projectes i Carpetes Personals | Bases de dades amb canvis constants i RPO/RTO de 4 h; documents i carpetes essencials, no poden perdre’s més de 24 h. |
| **Periodicitat (BD)**| Còpies cada 4 hores (incrementals) + completa setmanal          | Complim RPO de 4 hores i mantenim una còpia estable setmanal.             |
| **Tipus de Còpia (BD)** | Incremental diària (cada 4 h) + Completa setmanal + Completa mensual | Incremental permet freqüència alta i poc espai; la completa garanteix punts de restauració fiables. |
| **Mitjà 1 (Local)**  | NAS dins l’empresa                                               | Restauració ràpida per complir RTO de 4 hores; alta velocitat i automatització. |
| **Mitjà 2 (Extern)** | Còpia al Núvol (Cloud Backup)                                   | Garanteix la còpia “off-site” de la regla 3-2-1, protegint davant robatori, incendi o fallada total del local. |

