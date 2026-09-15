**PHASE 1 : GESTION DES INCIDENTS**



**Ticket 1** — **Serveur de messagerie**



Titre : Serveur de messagerie indisponible



Type : Incident

Catégorie : Messagerie

Impact : Très fort — toute l'entreprise est touchée

Urgence : Très forte

Priorité : Critique

SLA : SLA priorité critique

Description :



Le serveur de messagerie ne répond plus. L'ensemble des collaborateurs de l'entreprise est impacté et ne peut plus utiliser le service de messagerie.



Action : traitement immédiat.

&#x20;Pourquoi ? Impact maximal + urgence maximale = priorité critique.



**Ticket 2** **— Souris de la comptabilité**



Titre : Souris hors service — poste comptabilité



Type : Incident

Catégorie : Matériel 

Impact : Faible — un seul utilisateur

Urgence : Normale

Priorité :  Normale

SLA : SLA priorité normale

Description :



La souris du poste d'un collaborateur du service comptabilité ne fonctionne plus. Le problème concerne uniquement cet utilisateur.



Action : traitement après les incidents critiques.



Pourquoi ? Un seul utilisateur est touché il suffit de remplacer la souris 



**Ticket 3 — Email suspect** 



Celui-là est le piège de l'exercice.



Titre : Signalement d'un email suspect demandant des identifiants



Type :incident de sécurité

Catégorie : Sécurité 

Impact : Potentiellement fort

Urgence : Forte

Priorité : Haute

SLA : À traiter rapidement

Description :



Un collaborateur signale avoir reçu un email suspect lui demandant ses identifiants. Le message pourrait correspondre à une tentative de phishing. Une analyse du message et une vérification de sécurité sont nécessaires.



Action :



Ne pas cliquer sur les liens.

Conserver le message pour analyse.

Vérifier si d'autres utilisateurs ont reçu le même message.



Pourquoi ? Ce n'est pas une panne technique classique. On est face à un événement de sécurité potentiel.





**Ticket 4 — Imprimante du 2e étage**



Titre : Imprimante du 2e étage hors service



Type : Incident

Catégorie : Matériel 

Impact : Moyen — plusieurs utilisateurs potentiellement concernés

Urgence : Normale

Priorité : Moyenne

SLA : SLA priorité normale

Description :



L'imprimante située au 2e étage est hors service. Les utilisateurs concernés ne peuvent plus imprimer avec cet équipement.



Action : diagnostic de l'imprimante et vérification de sa disponibilité réseau.



Pourquoi ? L'impact est supérieur à celui de la souris car plusieurs personnes peuvent utiliser cette imprimante, mais l'entreprise entière n'est pas bloquée.



**Ticket 5 — DAF / tableau de bord financier**



Titre : Tableau de bord financier inaccessible pour le DAF



Type : Incident

Catégorie : Logiciel → Application métier

Impact : Fort — fonction financière

Urgence : Très forte

Priorité : Haute

SLA : SLA priorité critique si le tableau de bord est indispensable à l'activité immédiate

Description :



Le DAF ne parvient plus à ouvrir son tableau de bord financier. L'accès à l'outil financier est bloqué pour cet utilisateur.



Action : prise en charge rapide et vérification de l'application, des droits d'accès et de la connexion.



Pourquoi ? Même si une seule personne est concernée, l'urgence métier est très forte puisque le DAF est bloqué sur un outil financier. Ceux qui est assez urgent.



Ordre de traitement:

Ticket 1 — Serveur de messagerie           1

Ticket 3 — Email suspect                   2

Ticket 5 — DAF / tableau de bord financier 3

Ticket 4 — Imprimante du 2e étage          4 

Ticket 2 — Souris de la comptabilité       5





PHASE 2 : GESTION DES PROBLÈMES



**2. Les 5 pourquoi**



Pourquoi 1 ?



*Pourquoi le serveur mail tombe-t-il ?*



Parce qu'il devient d'abord très lent puis ne répond plus.



Pourquoi 2 ?



*Pourquoi devient-il très lent ?*



Parce que les ressources du serveur sont fortement sollicitées avant la coupure.



Pourquoi 3 ?



*Pourquoi les ressources sont-elles fortement sollicitées ?*



Parce qu'une charge importante s'accumule sur le serveur de messagerie.



Pourquoi 4 ?



*Pourquoi cette charge s'accumule-t-elle ?*



Parce que le serveur n'est pas suffisamment surveillé et qu'aucune action préventive n'est déclenchée avant d'atteindre un niveau critique.



Pourquoi 5 ?



*Pourquoi aucune action préventive n'est-elle déclenchée ?*



Parce qu'il n'existe pas de mécanisme de surveillance avec des seuils d'alerte permettant d'intervenir avant la saturation.





3\. *Workaround:*



Mettre en place une surveillance renforcée du serveur mail et redémarrer le service de messagerie dès l'apparition d'une forte dégradation afin de rétablir temporairement le service avant une coupure complète.



Objectif :



Limiter la durée d'indisponibilité du service en attendant la résolution définitive du problème.



**KEDB = une base des erreurs connues:**



ERREUR CONNUE : Serveur mail lent puis indisponible



SYMPTÔME :

Le serveur mail devient lent puis ne répond plus.



CAUSE :

Saturation des ressources du serveur.



WORKAROUND :

Redémarrer temporairement le service mail pour rétablir le service.



CORRECTION DÉFINITIVE :

Mettre en place une surveillance et corriger la cause de la saturation.



***PHASE 3 : GESTION DES CHANGEMENTS***



**RFC — Request for Change**

Titre:



Mise à jour critique du serveur de messagerie



Description



Le serveur de messagerie rencontre des incidents récurrents de lenteur suivie d'une coupure. La cause racine identifiée en phase 2 nécessite l'installation d'un correctif fourni par le fournisseur.



Objectif



Installer le correctif fourni par le fournisseur afin de corriger la cause du problème et éviter la répétition des incidents.



Impact:



Pendant la maintenance, le service de messagerie pourra être temporairement indisponible pour les utilisateurs.



Risques

Interruption temporaire de la messagerie.

Échec de l'installation du correctif.

Le correctif pourrait ne pas résoudre complètement le problème.

Risque de devoir restaurer la version précédente.



*Plan de rollback:*

Arrêter la mise à jour si une erreur apparaît.

Restaurer la version précédente du serveur.

Redémarrer le service de messagerie.

Vérifier que les utilisateurs peuvent de nouveau accéder à leur messagerie.

Documenter l'échec du changement dans GLPI.



Fenêtre de maintenance proposée:



Maintenance en dehors des heures ouvrées, par exemple le soir, afin de limiter l'impact sur les utilisateurs.





***PHASE 5 : GESTION DES DEMANDES DE SERVICE***



Dans GLPI, crée un nouveau ticket



Type :



Demande



Titre :



Onboarding IT — Julie, chargée de communication



Demandeur :



Julie



Description :



Nouveau collaborateur arrivant lundi prochain. Demande d'onboarding IT envoyée par le manager.

&#x20;Éléments à sélectionner



&#x20;Création compte utilisateur + boîte mail

&#x20;Attribution poste + périphériques

&#x20;Accès VPN

Accès au dossier partagé « Communication »



SLA:



le SLA est celui d'une demande de service, donc pas le SLA incident



Date cible:



Julie arrive lundi prochain.



Donc la date cible de mise à disposition doit être au plus tard lundi, avant son arrivée, afin que son environnement soit prêt dès son premier jour.





















