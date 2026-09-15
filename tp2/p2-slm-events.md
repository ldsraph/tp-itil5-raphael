## SLA / SLO proposés

- **SLA priorité critique** (panne bloquante, plusieurs utilisateurs impactés) : première réponse sous 30 min, résolution sous 4h — **SLO** : 95% des tickets critiques avec une première réponse en moins de 30 min.
- **SLA priorité normale** (demande standard, un seul utilisateur impacté) : première réponse sous 4h, résolution sous 2 jours ouvrés — **SLO** : 90% des tickets normaux résolus en moins de 2 jours ouvrés.

## Classification des logs

| Log | Classification | Justification | Action |
|---|---|---|---|
| `AUTH user=jdupont action=login status=success` | Informational | Connexion réussie, comportement normal, aucune anomalie | Aucune |
| `DISK host=SRV-FILE01 usage=82% threshold=80%` | Warning | Seuil dépassé de peu, pas d'impact utilisateur immédiat mais tendance à surveiller | Planifier une purge/extension de l'espace disque avant saturation |
| `SVC name=helpdesk-portal status=unreachable duration=00:04:12` | Exception | Le portail de tickets lui-même est inaccessible plus de 4 minutes : impact direct sur tous les utilisateurs qui veulent créer/suivre un ticket | Ouverture d'un Incident immédiat + vérification de la disponibilité du service |
| `BACKUP job=nightly-backup host=SRV-DB01 status=completed size=45GB` | Informational | Sauvegarde terminée avec succès, aucune anomalie | Aucune |
| `NET link=switch-3F-port12 status=down flapping=true count=6/10min` | Exception | Un lien réseau qui bascule 6 fois en 10 minutes indique une instabilité active, avec risque de coupures répétées pour les utilisateurs raccordés à ce switch | Ouverture d'un Incident + intervention réseau pour stabiliser le port avant qu'il ne cause des tickets en cascade |
