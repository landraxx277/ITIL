## SLA / SLO proposés

- **Priorité critique** (service indisponible, plusieurs utilisateurs bloqués) : première réponse sous 15 min, résolution sous 2h. SLO : 95% des tickets critiques répondus dans les 15 min, 90% résolus dans les 2h.
- **Priorité normale** (demande individuelle non bloquante) : première réponse sous 4h ouvrées, résolution sous 24h ouvrées. SLO : 90% des tickets normaux répondus dans les 4h.

## Classification des logs

- `AUTH login success` — **Informational**. Connexion réussie, comportement attendu. Aucune action.
- `DISK usage=82% threshold=80%` — **Warning**. Seuil dépassé de peu, pas d'impact immédiat mais tendance à surveiller. Action : planifier une purge des anciens fichiers.
- `SVC helpdesk-portal unreachable 4:12` — **Exception**. Le portail lui-même est inaccessible plus de 4 minutes, impact direct sur tous les utilisateurs. Action : ouverture d'un Incident.
- `BACKUP nightly-backup completed` — **Informational**. Sauvegarde réussie, rien à signaler.
- `NET switch-3F-port12 down, flapping, 6/10min` — **Exception**. Un lien qui flappe 6 fois en 10 minutes traduit une instabilité matérielle réelle, avec risque de coupures répétées. Action : ouverture d'un Incident et diagnostic du port/câble concerné.
