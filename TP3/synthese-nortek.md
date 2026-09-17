# Synthèse — TP "Une journée chez NORTEK SI"

**Phase 1.** Les 5 tickets ont été priorisés selon l'impact et l'urgence, pas selon leur ordre d'arrivée. Le mail HS et l'email de phishing passent en priorité majeure et sont traités en premier, le phishing avant le mail car les actions de confinement sont rapides et un retard peut avoir un effet cumulatif. Le tableau de bord du DAF suit grâce à son statut VIP, puis l'imprimante et la souris ferment la marche, les deux ayant un contournement disponible.

![Liste des tickets créés et priorisés dans GLPI](images/phase1-liste-tickets.png)

**Phase 2.** La récurrence de 3 pannes similaires en 2 semaines a justifié l'ouverture d'un Problème, lié aux 3 incidents concernés. Les 5 pourquoi ont permis de remonter à l'absence de purge automatique des logs, qui finit par saturer le disque et bloquer le service mail. Un workaround (purge manuelle et surveillance du disque) a été mis en place en attendant le correctif, et une entrée KEDB a été créée pour accélérer un futur diagnostic.

![Articles de base de connaissances liés aux tickets](images/phase2-base-connaissance.png)

**Phase 3.** La cause racine a donné lieu à une RFC de type Normal pour appliquer le correctif fournisseur, avec une fenêtre de maintenance de nuit et un plan de rollback basé sur une sauvegarde préalable. Le CAB a donné un avis favorable sous réserve qu'une restauration de test soit vérifiée avant l'intervention réelle. Le changement a été lié au Problème et aux incidents pour garder la traçabilité complète.

![Demande de validation et réponse du CAB sur le changement](images/phase3-validation-changement.png)

**Phase 4.** La fiche CI du serveur mail a été complétée avec ses dépendances (annuaire, sauvegarde nocturne, postes clients), ce qui a permis d'anticiper l'impact de la fenêtre de maintenance, en particulier sur la comptabilité et la direction financière.

![Analyse d'impact des CI liés au serveur mail](images/phase4-analyse-impact.png)

**Phase 5.** L'arrivée de Julie a été traitée comme une demande de service distincte des incidents, avec son propre catalogue (compte, poste, VPN, accès partagé) et un SLA orienté délai de mise à disposition plutôt que délai de résolution de panne.
