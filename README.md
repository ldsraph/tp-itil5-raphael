# Synthèse — TP ITIL 5 (helpdesk interne)

## Demande de service GLPI liée au changement

- **Titre** : Ajout d'une catégorie de ticket manquante dans la règle d'attribution automatique
- **Description** : Un technicien signale que les tickets liés aux imprimantes réseau ne correspondent à aucune catégorie existante dans la nouvelle règle de routage automatique et sont donc renvoyés dans la file commune sans assignation. Demande d'ajout de la catégorie « Périphériques réseau » avec assignation au groupe support matériel.
- **Statut** : Clôturé
- **Date de création** : 2026-09-11
- **Date de résolution** : 2026-09-12

Ce traitement relève de la pratique **Service Request Management** et non d'un Incident : il s'agit d'une demande planifiée d'ajustement de configuration, pas d'une panne de service.

## Tableau récapitulatif

| Partie | Pratique(s) mobilisée(s) |
|---|---|
| 1 | Continual Improvement |
| 2 | Service Level Management, Event Management |
| 3 | Change Enablement, Knowledge Management |
| 4 | Service Request Management |

## Principe directeur le plus structurant

« Se concentrer sur la valeur » : sur l'ensemble du cas, chaque choix a été évalué à l'aune du bénéfice réel perçu par l'utilisateur final plutôt que de la préférence technique de l'équipe support. L'exemple le plus concret est la priorisation en Partie 1 : la notification automatique de statut a été placée en priorité 1 devant l'attribution automatique des tickets, parce qu'elle traite directement l'irritant le plus visible pour l'utilisateur (les rappels dus au manque de visibilité), alors que l'attribution automatique — pourtant plus structurante côté processus interne — apporte un bénéfice moins immédiatement perceptible pour l'utilisateur final.

## AI Governance / 6C

Non pertinent dans l'état actuel du cas : aucune décision automatisée n'intervient dans le traitement des tickets décrit ici (les règles de routage et de notification sont déterministes, pas basées sur un modèle d'IA). Le module AI Governance et le référentiel 6C deviendraient pertinents si le helpdesk évoluait vers une catégorisation automatique des tickets par un modèle d'IA (par exemple pour deviner la catégorie d'un ticket à partir de sa description en texte libre) : se poserait alors une question de gouvernance concrète — qui valide et corrige les catégorisations erronées de l'IA, et comment on trace ces corrections pour éviter qu'une mauvaise catégorisation automatique ne reproduise le problème de tickets mal routés que ce TP cherche justement à corriger.
