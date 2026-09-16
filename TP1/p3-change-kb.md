## RFC — Règle de rapprochement automatique des tickets dupliqués

- **Type** : Normal. Le changement touche le comportement de création de ticket pour tous les utilisateurs et techniciens, il demande donc une évaluation, sans avoir l'urgence ni le faible risque d'un changement standard.
- **Impact** : tous les techniciens (nouvelle alerte à traiter) et tous les utilisateurs internes. Risque principal : un faux rapprochement qui fusionnerait deux demandes réellement distinctes du même utilisateur dans la fenêtre de 24h.
- **Plan de rollback** : déploiement en mode « suggestion » pendant deux semaines — le technicien valide manuellement chaque fusion. Si le taux de faux positifs est trop élevé, la règle est désactivée et le traitement repasse en création indépendante, sans perte de données puisque les tickets sources restent inchangés tant que la fusion n'est pas validée.
- **CAB simulé** : le demandeur juge que le volume de rappels liés aux doublons justifie un déploiement rapide, la phase suggestion limitant le risque de fusion abusive. L'approbateur valide, mais conditionne le passage en fusion automatique à une revue du taux de faux positifs après deux semaines.

## Article de base de connaissance

- **Symptôme** : un même incident est signalé plusieurs fois par le même utilisateur (mail puis téléphone, ou deux mails successifs).
- **Cause** : rien ne rapproche les tickets à la création, le technicien qui traite le second n'a pas de visibilité sur le premier.
- **Résolution** : consulter la suggestion de rapprochement affichée sur les tickets liés au même utilisateur dans les 24h, et valider ou rejeter la fusion avant de poursuivre.
- **Mots-clés** : ticket dupliqué, doublon, rapprochement, plusieurs canaux.

## Positionnement dans le Product and Service Lifecycle

Ce changement mobilise surtout **Build** (paramétrage de la règle) et **Transition** (déploiement progressif, formation des techniciens). Un lien avec **Design** apparaîtrait si le retour d'expérience conduisait à repenser plus largement la qualification des tickets à la création, plutôt qu'à corriger un symptôme après coup — ce qui montre bien que ces étapes ne s'enchaînent pas de façon linéaire : Build et Transition peuvent boucler plusieurs fois avant un éventuel retour vers Design.
