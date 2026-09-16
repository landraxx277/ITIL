## Demande de service GLPI

- **Type** : Demande
- **Titre** : Activer la règle de rapprochement automatique des tickets (mode suggestion)
- **Catégorie** : Support > Ticketing > Paramétrage
- **Statut** : Clos
- **Urgence / Impact / Priorité** : Moyenne / Moyen / Moyenne
- **Demandeur** : Responsable helpdesk — **Attribué à** : Technicien référent outil de ticketing
- **Dates** : ouverture J, échéance SLA J+7, résolution J+6, clôture J+20 (après la période de suivi des faux positifs)

**Description**

Suite à la RFC validée par le CAB, paramétrer la règle de rapprochement des tickets créés par un même utilisateur sur 24h, en mode « suggestion » : le technicien voit une alerte mais valide manuellement la fusion, sans automatisme. Une note de formation courte est prévue pour les techniciens.

**Tâches réalisées**

Règle paramétrée en test le J+1, sur le critère même demandeur + fenêtre 24h. Test validé le J+3 sur 10 cas de rapprochement correct, avec un seul faux positif (deux demandes réellement distinctes du même utilisateur le même jour) — jugé acceptable puisque la fusion reste manuelle. Déploiement en production le J+5, en dehors des heures de pointe. Note de formation diffusée le J+6, par mail et lors du point d'équipe. Suivi réalisé à J+14 : 23 alertes déclenchées, 21 fusions validées, 2 rejetées, soit un taux de faux positifs d'environ 9%, jugé acceptable au vu du gain de temps observé.

**Solution**

Règle déployée et adoptée en mode suggestion. Le taux de faux positifs mesuré étant sous le seuil de tolérance fixé avec l'approbateur, le passage en fusion automatique est proposé comme amélioration de suite plutôt que traité dans ce ticket, qui est clôturé sur son périmètre initial.

**Suivi**

Ticket rattaché à la RFC de la Partie 3 — c'est une demande planifiée découlant d'un changement approuvé, pas un Incident, d'où son traitement via Service Request Management. Aucune régression signalée sur la création normale de tickets. Clôturé par le demandeur après confirmation que la réduction des rappels liés aux doublons est bien observée sur le terrain.
