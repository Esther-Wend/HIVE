# HIVE
Dans le cadre de ma formation sur BLENT,   jai été amené à créer un datawarehouse sur HIVE en passant par le DATAPROC de GCP


Importer les données dans Hive

Les données récoltées sont au format CSV. Le schéma des données n'est donc pas présent : il faut tout d'abord créer les tables sous Hive, puis importer les données CSV dans les tables créées.

Construire la table dénormalisée des emprunts

Les données récoltées dans le cadre de ce projet ont été normalisées selon un schéma 1NF avec deux tables de données à dispositions.

La table loans contient des informations statiques sur les emprunts.
La table loans_data contient les informations financières sur chacun des emprunts de la première table.
La banque a besoin d'une seule table dénormalisée avec des informations. En fonction des besoins pour les requêtes HQL, il se peut que plusieurs lignes apparaissent avec des informations identiques lorsque le statut de l'emprunt change, ou que de nouveaux montants sont remboursés.

Construire les requêtes HQL sur la table dénormalisée

Dans l'optique de faire gagner du temps aux équipes métiers, l'entreprise souhaite disposer de requêtes pré-enregistrées sous forme de fichier HQL, de sorte que ces derniers puissent facilement exécuter des requêtes en modifiant un ou deux paramètres d'entrée. Les requêtes HQL qui doivent être implémentées sont les suivantes.

Pour chacune des organisations ayant emprunté (Borrower) au cours des 10 dernières années, déterminer le taux de prêts non recouverts. Cette information peut être obtenue en comparant le montant déboursé avec le montant du remboursement à l'IBRD.
Calculer le taux d'intérêt moyen accordé par l'IBRD chaque mois à l'ensemble des emprunteurs.
Déterminer, pour un emprunt (Borrower), la durée moyenne de recouvrement des emprunts.
