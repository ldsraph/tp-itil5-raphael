## RFC — Mise en place d'une règle d'attribution automatique des tickets

- **Type** : Normal (le changement modifie le processus de travail de toute l'équipe support et nécessite une évaluation avant déploiement ; ce n'est ni un ajustement pré-approuvé à faible risque, ni une urgence).
- **Impact** : tous les techniciens de niveau 1, dont la charge de travail va être redistribuée automatiquement ; risque de mauvaise catégorisation initiale (un ticket mal étiqueté à l'ouverture serait routé vers le mauvais technicien) et risque temporaire de sur-attribution à un technicien si les règles de pondération ne sont pas correctement calibrées.
- **Plan de rollback** : conservation en parallèle de l'attribution manuelle pendant 2 semaines après l'activation ; la règle automatique peut être désactivée en un clic dans GLPI, ce qui fait immédiatement revenir au fonctionnement actuel sans perte des tickets déjà routés (ils restent visibles et réassignables manuellement).
- **Validation CAB simulée** :
  - Demandeur : « Le délai moyen d'attribution d'un ticket est actuellement de plusieurs heures ; l'automatisation le ramène à quelques minutes et réduit directement le risque de tickets oubliés. »
  - Approbateur : « D'accord sur le principe, mais il faut d'abord valider les règles de catégorisation sur un mois de tickets historiques en environnement de test avant toute activation en production, pour éviter les mauvais routages en conditions réelles. »

## Article de base de connaissance

- **Symptôme** : un ticket reste visible dans la file commune sans qu'aucun technicien ne le prenne en charge pendant plusieurs heures.
- **Cause** : absence de règle d'attribution automatique dans GLPI ; le ticket dépend entièrement de la prise en charge manuelle et spontanée par un technicien disponible.
- **Résolution** : activation de la règle de routage automatique par catégorie/compétence dans GLPI, qui assigne le ticket à un technicien dès sa création selon son type.
- **Mots-clés** : ticket non assigné, attribution automatique, routage GLPI, file d'attente.

## Positionnement dans le Product and Service Lifecycle

Ce changement mobilise principalement les étapes **Build** (paramétrage des règles de routage dans GLPI) et **Transition** (déploiement progressif, formation des techniciens aux nouvelles règles d'assignation). Un lien avec **Design** est également justifié à la marge : redéfinir qui reçoit quel type de ticket revient à repenser une partie du workflow de traitement, pas seulement à automatiser une étape existante à l'identique.

Ce modèle n'est pas un enchaînement strictement linéaire : ici, la phase de test des règles de catégorisation (qui relève déjà de Build) doit se dérouler avant la fin de la Transition, et un retour en arrière vers Design resterait possible si les tests montrent que la logique de catégorisation initiale doit être revue — les étapes se chevauchent selon les retours obtenus en cours de route.
