
   # Rendez-vous dans mon repository Github pour avoir acces aux ressources :
   ```bash
   https://github.com/medbankole97/ABC-Corporation.git

   

   git clone https://github.com/medbankole97/ABC-Corporation.git
   ```

 # 1-Organisation du Projet
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

> Ceci un fichier


# 2-Étapes pour Prendre en Main le Projet
## Instructions d'Installation


  ### - Prérequis :
	Un SGBDR (Système de Gestion de Base de Données Relationnelle) tel que MySQL
	Accès aux scripts SQL et aux ressources documentaires



**Pour se connecter aux mysql**
![](./Images/connexionmysql.PNG)

**La connexion est réussie**
![](./Images/connReussi.PNG)

**Creation de la base de données**
![](./Images/1-createdb.PNG)

**Utilisé la bade de données et lister pour confirmer son existance**
![](./Images/etape1.PNG)

**Creation de la table customers et products**
![](./Images/etape2.PNG)

**Creation de la table purchase_orders et order_details**
![](./Images/etape3.PNG)

## Fin de création de la base de données



# Les requetes sql pour la creation de base de données et des tables :

### les différentes étapes

```créarion de la base de données
CREATE DATABASE order_management;
```

```utiliser la bdd
USE order_management;
```

```table customers
CREATE TABLE customers (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(50) NOT NULL,
    address VARCHAR(50) NOT NULL,
    email VARCHAR(50) NOT NULL UNIQUE,
    phone VARCHAR(30) NOT NULL UNIQUE
);
```
```table products
CREATE TABLE products (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(50) NOT NULL,
    description VARCHAR(100) NOT NULL,
    price DECIMAL(10,2) NOT NULL,
    stock INT NOT NULL
);
```
```table purchase_orders
CREATE TABLE purchase_orders (
    id INT AUTO_INCREMENT PRIMARY KEY,
    order_date DATE NOT NULL,
    delivery_address VARCHAR(50) NOT NULL,
    customer_id INT NOT NULL,
    FOREIGN KEY (customer_id) REFERENCES customers(id)
);
```
```table order_details
CREATE TABLE order_details (
    id INT AUTO_INCREMENT PRIMARY KEY,
    quantity INT NOT NULL,
    price DECIMAL(10,2) NOT NULL,
    order_id INT NOT NULL,
    product_id INT NOT NULL,
    FOREIGN KEY (order_id) REFERENCES purchase_orders(id),
    FOREIGN KEY (product_id) REFERENCES products(id)
);
```
  # 3-Points d’Améliorations Possibles
    Automatisation de la Migration des Données :

    Développer des scripts pour automatiser la migration des données depuis différents formats de fichiers (CSV, Excel, etc.).
    Optimisation des Performances :

    Ajouter des index sur les colonnes fréquemment utilisées dans les requêtes pour améliorer les performances.



    Ajouter une documentation détaillée pour les développeurs et les utilisateurs finaux.
    Inclure des tutoriels et des guides d’utilisation pour faciliter la prise en main du système.
