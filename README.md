# 📘 TP_SparkSQL (TP4 Spark SQL)

**Auteur :** Othmane Mefrah  
**Technologies :** Apache Spark SQL, Java, Maven

---

## 🧭 Table des matières

1. Présentation  
2. Prérequis  
3. Installation & Exécution  
4. Détails du TP  
5. Résultats attendus  
6. Structure du dépôt  
7. Licence

---

## 1. Présentation

Ce projet est une application Spark SQL développée dans le cadre du TP4 sur le traitement de données structurelles. Son objectif :

- Lire un fichier CSV contenant des incidents (id, titre, description, service, date)
- Réaliser des analyses SQL (groupement, agrégation, extraction d’année)
- Exporter les résultats en fichiers CSV

---

## 2. Prérequis

Avant de démarrer, assure-toi d’avoir installé :

- 🖥️ **Java JDK 11+**  
- 🔧 **Maven**  
- 🧰 **Apache Spark 3.x** (lors du run en local)  
- 📦 **Docker** + **Spark cluster (bitnami/spark)** si utilisation en cluster  
- ✅ **winutils.exe** configuré sur Windows (HADOOP_HOME)

---

## 3. Installation & Exécution

a) Construire le projet

mvn clean package

b) Exécution locale (IntelliJ ou ligne de commande)

java -cp target/TP-4-Spark-SQL-1.0-SNAPSHOT.jar org.example.App

Ou via IntelliJ avec les configurations Run
4. Détails du TP
🔹 App.java – analyse Spark SQL

    Création d’un SparkSession en mode local

    Lecture du CSV incidents.csv avec header + inférence de schéma

    Création d'une table temporaire incidents

    Requêtes SQL exécutées :

        Nombre d’incidents par service

        Deux années avec le plus d’incidents

    Affichage console + export CSV dans output/

5. Résultats attendus
✔️ Console :

➡️ Nombre d'incidents par service:
+-----------+------------+
| service   | nb_incidents |
+-----------+------------+
| production|     2      |
| maintenance|    1      |
| qualité   |     2      |
+-----------+------------+

➡️ Les deux années avec le plus d'incidents:
+------+------+
| annee| total|
+------+------+
| 2023 |  3   |
| 2022 |  2   |
+------+------+

✔️ Fichiers CSV générés :

output/
├── incidents_par_service/part-*.csv
└── top_2_annees/part-*.csv

6. Structure du dépôt

TP_SparkSQL/
├── src/
│   └── main/
│       └── java/
│           └── org/
│               └── example/
│                   └── App.java
├── src/main/resources/
│   └── incidents.csv
├── output/ (généré automatiquement)
├── pom.xml
└── README.md

7. Licence

Ce TP est libre à l’usage académique.
Pour tout usage commercial, merci de mentionner l’auteur
