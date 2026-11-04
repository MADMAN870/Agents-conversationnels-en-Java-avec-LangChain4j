# Agents conversationnels en Java avec LangChain4j

## Présentation

Ce projet consiste à développer une application web d'agents conversationnels en Java, basée sur Jakarta EE, Jakarta Faces (JSF), CDI et Payara Server.

L'application permet à l'utilisateur d'interagir avec différents agents conversationnels en fonction du rôle système sélectionné.

## Technologies utilisées

- **Java** : langage de programmation.

- **Maven** : gestion des dépendances et compilation.

- **Jakarta EE** : plateforme de développement d'applications web Java.

- **Jakarta Faces (JSF)** : création de l'interface web.

- **CDI** : injection de dépendances et gestion du cycle de vie des composants.

- **Payara Server 7** : serveur d'applications.

- **LangChain4j** : intégration prévue avec des modèles de langage (LLM).

## Prérequis

Avant de lancer le projet, assurez-vous de disposer des éléments suivants :

- JDK 17 ou une version compatible avec Payara Server.

- Maven 3.9+ (ou utiliser le Maven Wrapper fourni).

- Payara Server 7.

## Structure du projet

```
tp0/

├── src/

│   └── main/

│       ├── java/com/example/tpjsf/

│       │   ├── Bb.java

│       │   └── GenerateurResponse.java

│       └── webapp/

│           ├── WEB-INF/

│           ├── resources/

│           └── index.xhtml

├── pom.xml

└── README.md
```

## Installation et exécution

### 1. Cloner le dépôt

```
git clone git@github.com:MADMAN870/Agents-conversationnels-en-Java-avec-LangChain4j.git


cd Agents-conversationnels-en-Java-avec-LangChain4j
```

### 2. Compiler le projet

À la racine du projet, exécutez :

```
./mvnw clean package
```

Cette commande compile le projet et génère un fichier WAR prêt à être déployé.

Le fichier WAR se trouve dans le répertoire :

```
target/tp-jsf.war
```

### 3. Démarrer Payara Server

Démarrez le domaine Payara :

```
asadmin start-domain domain1
```

Si la commande `asadmin` n'est pas disponible dans votre PATH, utilisez le chemin correspondant à votre installation de Payara.

Exemple sous Linux :

```
~/.local/opt/payara-7.2026.9/glassfish/bin/asadmin start-domain domain1
```

### 4. Déployer l'application

Depuis la racine du projet, exécutez :

```
asadmin deploy --force=true target/tp-jsf.war
```

Exemple sous Linux avec le chemin d'installation précédent :

```
~/.local/opt/payara-7.2026.9/glassfish/bin/asadmin deploy --force=true target/tp-jsf.war
```

L'option `--force=true` permet de remplacer une version déjà déployée de l'application.

### 5. Accéder à l'application

Une fois le déploiement terminé, ouvrez votre navigateur à l'adresse suivante :

**[http://localhost:8080/tp-jsf/index.xhtml**](http://localhost:8080/tp-jsf/index.xhtml)

### 6. Arrêter Payara Server

Pour arrêter le domaine lorsque vous avez terminé :

```
asadmin stop-domain domain1
```

## Fonctionnalités actuelles

- Interface web conversationnelle développée avec JSF.

- Sélection du rôle système de l'agent :

  - Assistant conversationnel.

  - Traducteur anglais-français.

  - Guide touristique.

- Gestion de l'historique des conversations.

- Possibilité de démarrer une nouvelle conversation.

- Mode debug.

- Génération de réponses de test.

## État du développement

Le projet est actuellement en cours de développement.

Le générateur de réponses utilise pour le moment des réponses prédéfinies afin de tester le fonctionnement de l'application et de son architecture.

L'intégration de modèles de langage (LLM) à travers **LangChain4j** constitue une prochaine étape du développement.

## Auteur

**MADMAN870**

