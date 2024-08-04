
 Conception d'une base de données pour centraliser et automatiser les opérations commerciales d'ABC Corporation.

    ### Organisation du Projet
     Après avoir analysé les ressources fournies, le projet a été organisé et planifié sur Trello. Les tâches ont été décomposées comme suit :

	1-Téléchargement et analyse des ressources
	2- Réalisation du dictionnaire de données
            - Création d'un document détaillant les entités et leurs attributs.
            - Outils utilisés : Google Sheets.
	3- Conception du Modèle Conceptuel de Données (MCD)
            - Utilisation d'un outil de modélisation pour concevoir le MCD.
            - Outils utilisés : Looping.
	4- Transformation du MCD en Modèle Logique de Données (MLD)
            
	5- Création d'un fichier SQL contenant les scripts pour créer la base de données et les tables
            - Écriture des scripts SQL pour créer la base de données et les tables.
            - Outils utilisés : MySQL ( en mode console ).

   ### Étapes pour Prendre en Main le Projet
	- Prérequis :
	Un SGBDR (Système de Gestion de Base de Données Relationnelle) tel que MySQL
	Accès aux scripts SQL et aux ressources documentaires
   
        - Étapes :
       1- Choisir et installer un SGBDR (par exemple MySQL).

       2- Créer la base de données :
	CREATE DATABASE order_management;   //(nom de la base de données : order_management)  
	
       3- Utiliser la base de données créée :
        USE order_management;
	
       4- Créer une  table :   	
        
       CREATE TABLE customers (
       id INT AUTO_INCREMENT PRIMARY KEY,
       customer_name VARCHAR(50) NOT NULL,
       address VARCHAR(50) NOT NULL,
       email VARCHAR(50) NOT NULL UNIQUE,
      phone VARCHAR(30) NOT NULL UNIQUE);
      

//customers comme nom de la table
      
      5- Insérer des données dans la table customers :
       INSERT INTO customers (customer_name, address, email, phone)  VALUES 
       ('Mohamed Bankolé', 'Nktt pk8', 'medbankole97@gmail.com', '41 74 07 87');

      6- Si vous souhaitez ajouter une contrainte d'unicité sur les colonnes email et phone après la création de la table, utilisez le script suivant :

      - ALTER TABLE customers ADD CONSTRAINT unique_email UNIQUE (email);
      - ALTER TABLE customers ADD CONSTRAINT unique_phone UNIQUE (phone);



     ### Points d’Améliorations Possibles
    Automatisation de la Migration des Données :

    Développer des scripts pour automatiser la migration des données depuis différents formats de fichiers (CSV, Excel, etc.).
    Optimisation des Performances :

    Ajouter des index sur les colonnes fréquemment utilisées dans les requêtes pour améliorer les performances.



    Ajouter une documentation détaillée pour les développeurs et les utilisateurs finaux.
    Inclure des tutoriels et des guides d’utilisation pour faciliter la prise en main du système.


   ### Ressources Utilisées
   Site officiel de MySQL
   Tutoriels MySQL sur W3Schools : W3Schools MySQL Tutorial
   Trello pour la gestion des tâches : Trello

   


    Ce projet a permis de centraliser et d'automatiser les opérations commerciales d'ABC Corporation, améliorant ainsi l'efficacité et la gestion des données. En suivant les étapes décrites ci-dessus et en mettant en œuvre les points d'améliorations suggérés, ABC Corporation pourra continuer à optimiser ses processus et à répondre aux besoins croissants de ses opérations commerciales.   



