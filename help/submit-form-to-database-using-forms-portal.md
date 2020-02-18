---
title: Envoyer des formulaires adaptatifs à la base de données à l’aide de Forms Portal
description: Etendez le méta-modèle par défaut pour ajouter des modèles, des validations et des entités spécifiques à votre organisation et appliquer des configurations aux champs de formulaire adaptatif lors de l’exécution du service de conversion automatisée des formulaires.
uuid: f98b4cca-f0a3-4db8-aef2-39b8ae462628
topic-tags: forms
discoiquuid: cad72699-4a4b-4c52-88a5-217298490a7c
translation-type: tm+mt
source-git-commit: 040b0ddb489b5bdfd640a93b22cd7bc512a39aea

---


# Intégration de formulaires adaptatifs à une base de données à l’aide de Forms Portal {#submit-forms-to-database-using-forms-portal}

Le service de conversion automatisée de formulaires vous permet de convertir un formulaire PDF non interactif, un formulaire Acro ou un formulaire PDF XFA en formulaire adaptatif. Lors du lancement du processus de conversion, vous avez la possibilité de générer un formulaire adaptatif avec ou sans liaisons de données.

Si vous choisissez de générer un formulaire adaptatif sans liaison de données, vous pouvez intégrer le formulaire adaptatif converti à un modèle de données de formulaire, un schéma XML ou un schéma JSON après la conversion. Cependant, si vous générez un formulaire adaptatif avec des liaisons de données, le service de conversion associe automatiquement le ou les formulaires adaptatifs à un schéma JSON et crée une liaison de données entre les champs disponibles dans le formulaire adaptatif et le schéma JSON. Vous pouvez ensuite intégrer le formulaire adaptatif à une base de données de votre choix, remplir les données du formulaire et les envoyer à la base de données à l’aide de Forms Portal.

La figure suivante illustre les différentes étapes de l’intégration d’un formulaire adaptatif converti à une base de données à l’aide de Forms Portal :

![intégration de base de données](assets/database_integration.gif)

Cet article décrit les instructions étape par étape pour exécuter toutes ces étapes d’intégration.

L’exemple présenté dans cet article est une implémentation de référence de services de données et de métadonnées personnalisés pour intégrer une page Forms Portal à une base de données. La base de données utilisée dans l’exemple d’implémentation est MySQL 5.6.24. Vous pouvez toutefois intégrer la page Forms Portal à n’importe quelle base de données de votre choix.

## Conditions préalables {#pre-requisites}

* Instance d’auteur AEM 6.5 avec la dernière version d’AEM 6.5 Service Pack
* Dernière version du module complémentaire AEM Forms
* [Service de conversion de formulaires automatisés](configure-service.md)
* Base de données à intégrer. La base de données utilisée dans l’exemple d’implémentation est MySQL 5.6.24. Vous pouvez toutefois intégrer Forms Portal à n’importe quelle base de données de votre choix.

## Configurer la connexion entre l’instance AEM et la base de données {#set-up-connection-aem-instance-database}

La configuration d’une connexion entre une instance AEM et une base de données MYSQL consiste à :

* [Installation d’un package de connecteur MYSQL](#install-mysql-connector-java-file)

* [Création de schémas et de tableaux dans la base de données](#create-schema-and-tables-in-database)

* [Configuration des paramètres de connexion](#configure-connection-between-aem-instance-and-database)

* [Configuration et configuration du modèle de package pour l’intégration de Forms Portal](#set-up-and-configure-sample)

### Installez le fichier mysql-connector-java-5.1.39-bin.jar.{#install-mysql-connector-java-file}

Effectuez les étapes suivantes, sur toutes les instances d’auteur et de publication, pour installer le fichier mysql-connector-java-5.1.39-bin.jar :

1. Navigate to http://[server]:[port]/system/console/depfinder and search for com.mysql.jdbc package.
1. Dans la colonne Exporté par, vérifiez si le package est exporté par un groupe. Continuez si le package n’est pas exporté par un groupe.
1. Navigate to http://[server]:[port]/system/console/bundles and click **[!UICONTROL Install/Update]**.
1. Click **[!UICONTROL Choose File]** and browse to select the mysql-connector-java-5.1.39-bin.jar file. Sélectionnez également **[!UICONTROL Start Bundle]** et **[!UICONTROL Refresh Packages]** cochez les cases.
1. Cliquez sur **[!UICONTROL Install]** ou **[!UICONTROL Update]**. Une fois cette opération effectuée, redémarrez le serveur.
1. (Windows uniquement) Désactivez le pare-feu système pour votre système d’exploitation.

### Création de schémas et de tableaux dans la base de données {#create-schema-and-tables-in-database}

Pour créer un schéma et des tables dans la base de données, procédez comme suit :

1. Créez un schéma dans la base de données à l’aide de l’instruction SQL suivante :

   ```sql
   CREATE SCHEMA `formsportal` ;
   ```

   où **formsportal** fait référence au nom du schéma.

1. Créez une table de **données** dans le schéma de base de données à l’aide de l’instruction SQL suivante :

   ```sql
    CREATE TABLE `data` (
        `owner` varchar(255) DEFAULT NULL,
        `data` longblob,
        `metadataId` varchar(45) DEFAULT NULL,
        `id` varchar(45) NOT NULL,
        PRIMARY KEY (`id`)
        ) ENGINE=InnoDB DEFAULT CHARSET=utf8;
   ```

1. Créez une table de **métadonnées** dans le schéma de base de données à l’aide de l’instruction SQL suivante :

   ```sql
   CREATE TABLE `metadata` (
       `formPath` varchar(1000) DEFAULT NULL,
       `formType` varchar(100) DEFAULT NULL,
       `description` text,
       `formName` varchar(255) DEFAULT NULL,
       `owner` varchar(255) DEFAULT NULL,
       `enableAnonymousSave` varchar(45) DEFAULT NULL,
       `renderPath` varchar(1000) DEFAULT NULL,
       `nodeType` varchar(45) DEFAULT NULL,
       `charset` varchar(45) DEFAULT NULL,
       `userdataID` varchar(45) DEFAULT NULL,
       `status` varchar(45) DEFAULT NULL,
       `formmodel` varchar(45) DEFAULT NULL,
       `markedForDeletion` varchar(45) DEFAULT NULL,
       `showDorClass` varchar(255) DEFAULT NULL,
       `sling:resourceType` varchar(1000) DEFAULT NULL,
       `attachmentList` longtext,
       `draftID` varchar(45) DEFAULT NULL,
       `submitID` varchar(45) DEFAULT NULL,
       `id` varchar(60) NOT NULL,
       `profile` varchar(255) DEFAULT NULL,
       `submitUrl` varchar(1000) DEFAULT NULL,
       `xdpRef` varchar(1000) DEFAULT NULL,
       `agreementId` varchar(255) DEFAULT NULL,
       `nextSigners` varchar(255) DEFAULT NULL,
       `eSignStatus` varchar(45) DEFAULT NULL,
       `pendingSignID` varchar(45) DEFAULT NULL,
       `agreementDataId` varchar(255) DEFAULT NULL,
       `enablePortalSubmit` varchar(45) DEFAULT NULL,
       `submitType` varchar(45) DEFAULT NULL,
       `dataType` varchar(45) DEFAULT NULL,
       `jcr:lastModified` varchar(45) DEFAULT NULL,
       PRIMARY KEY (`id`),
       UNIQUE KEY `ID_UNIQUE` (`id`)
       ) ENGINE=InnoDB DEFAULT CHARSET=utf8;
   ```

1. Créez une table **supplémentaire** métadatable dans le schéma de base de données à l’aide de l’instruction SQL suivante :

   ```sql
   CREATE TABLE `additionalmetadatatable` (
       `value` text,
       `key` varchar(255) NOT NULL,
       `id` varchar(60) NOT NULL,
       PRIMARY KEY (`id`,`key`),
       CONSTRAINT ‘additionalmetadatatable_fk’ FOREIGN KEY (`id`) REFERENCES `metadata` (`id`) ON DELETE CASCADE
       ) ENGINE=InnoDB DEFAULT CHARSET=utf8;
   ```

1. Créez une table **commentable** dans le schéma de base de données à l’aide de l’instruction SQL suivante :

   ```sql
   CREATE TABLE `commenttable` (
       `commentId` varchar(255) DEFAULT NULL,
       `comment` text DEFAULT NULL,
       `ID` varchar(255) DEFAULT NULL,
       `commentowner` varchar(255) DEFAULT NULL,
       `time` varchar(255) DEFAULT NULL);
   ```

### Configurer la connexion entre l’instance AEM et la base de données {#configure-connection-between-aem-instance-and-database}

Effectuez les étapes de configuration suivantes pour créer une connexion entre l’instance AEM et la base de données MYSQL :

1. Go to AEM Web Console Configuration page at *http://[host]:[port]/system/console/configMgr*.
1. Cliquez pour ouvrir **[!UICONTROL Forms Portal Draft and Submission Configuration]** en mode d’édition.
1. Spécifiez les valeurs des propriétés comme décrit dans le tableau suivant :   

   <table> 
    <tbody> 
    <tr> 
    <th><strong>Propriétés</strong></th> 
    <th><strong>Description</strong></th>
    <th><strong>Valeur</strong></th> 
    </tr> 
    <tr> 
    <td><p>Service de données de brouillon du portail Forms </p></td> 
    <td><p>Identifiant du service de données de brouillon</p></td>
    <td><p>formsportal.sampledataservice</p></td> 
    </tr>
    <tr> 
    <td><p>Service de métadonnées de brouillon du portail Forms </p></td> 
    <td><p>Identifiant du service de métadonnées de brouillon</p></td>
    <td><p>formsportal.samplemetadataservice</p></td> 
    </tr>
    <tr> 
    <td><p>Service de données d’envoi du portail Forms</p></td> 
    <td><p>Identifiant du service de données d’envoi</p></td>
    <td><p>formsportal.sampledataservice</p></td> 
    </tr>
    <tr> 
    <td><p>Service de métadonnées d’envoi du portail Forms </p></td> 
    <td><p>Identifiant du service de métadonnées d’envoi</p></td>
    <td><p>formsportal.samplemetadataservice</p></td> 
    </tr>
    <tr> 
    <td><p>Service de données de signature en attente du portail Forms</p></td> 
    <td><p>Identificateur pour le service de données de signature en attente</p></td>
    <td><p>formsportal.sampledataservice</p></td> 
    </tr>
    <tr> 
    <td><p>Service de métadonnées de signature en attente du portail Forms</p></td> 
    <td><p>Identificateur du service de métadonnées de signature en attente</p></td>
    <td><p>formsportal.samplemetadataservice</p></td> 
    </tr>
    </tbody> 
    </table>
1. Leave other configurations as is and click **[!UICONTROL Save]**.
1. Recherchez et cliquez pour ouvrir **[!UICONTROL Apache Sling Connection Pooled DataSource]** en mode d’édition dans la configuration de la console Web. Spécifiez les valeurs des propriétés comme décrit dans le tableau suivant :   

   <table> 
    <tbody> 
    <tr> 
    <th><strong>Propriétés</strong></th> 
    <th><strong>Valeur</strong></th> 
    </tr> 
    <tr> 
    <td><p>Nom de la source de données </p></td> 
    <td><p>Un nom de source de données pour filtrer les pilotes du pool de la source de données  . L’exemple d’implémentation utilise FormsPortal comme nom de source de données.</p></td>
    </tr>
    <tr> 
    <td><p>Classe de pilote JDBC </p></td> 
    <td><p>com.mysql.jdbc.Driver</p></td>
    </tr>
    <tr> 
    <td><p>URI de connexion JDBC</p></td> 
    <td><p>jdbc:mysql://[hôte]:[port]/[nom_schéma]</p></td>
    </tr>
    <tr> 
    <td><p>username</p></td> 
    <td><p>Un nom d’utilisateur pour s’authentifier et effectuer des opérations sur les tableaux de base de données </p></td>
    </tr>
    <tr> 
    <td><p>Mot de passe</p></td> 
    <td><p>Mot de passe associé au nom d’utilisateur </p></td>
    </tr>
    <tr> 
    <td><p>isolation de transaction</p></td> 
    <td><p>READ_COMMITTED</p></td>
    </tr>
    <tr> 
    <td><p>Nombre maximum de connexions actives</p></td> 
    <td><p>1000</p></td>
    </tr>
    <tr> 
    <td><p>Nombre maximum de connexions inactives</p></td> 
    <td><p>100</p></td>
    </tr>
    <tr> 
    <td><p>Nombre minimum de connexions inactives</p></td> 
    <td><p>10</p></td>
    </tr>
    <tr> 
    <td><p>Taille initiale</p></td> 
    <td><p>10</p></td>
    </tr>
    <tr> 
    <td><p>Attente maximale</p></td> 
    <td><p>100 000</p></td>
    </tr>
     <tr> 
    <td><p>Test lors de l’emprunt</p></td> 
    <td><p>Cochée</p></td>
    </tr>
     <tr> 
    <td><p>Tester lors de l’inactivité</p></td> 
    <td><p>Cochée</p></td>
    </tr>
     <tr> 
    <td><p>Requête de validation</p></td> 
    <td><p>Les valeurs d’exemple sont SELECT 1(mysql), select 1 from dual(oracle), SELECT 1(MS Sql Server) (validationQuery)</p></td>
    </tr>
     <tr> 
    <td><p>Délai d’expiration de la requête de validation</p></td> 
    <td><p>10 000</p></td>
    </tr>
    </tbody> 
    </table>

### Installation et configuration de l&#39;exemple{#set-up-and-configure-sample} 

Effectuez les étapes suivantes, sur toutes les instances d’auteur et de publication, pour installer et configurer l’exemple :

1. Téléchargez le package suivant **aem-fp-db-integration-sample-pkg-6.1.2.zip** vers votre système de fichiers.

   [Obtenir le fichier](assets/aem-fp-db-integration-sample-pkg-6.1.2.zip)

1. Go to AEM package manager at *http://[host]:[port]/crx/packmgr/*.
1. Cliquez sur **[!UICONTROL Upload Package]**.
1. Parcourez l’arborescence pour sélectionner le package **aem-fp-db-integration-sample-pkg-6.1.2.zip** et cliquez sur **[!UICONTROL OK]**.
1. Click **[!UICONTROL Install]** next to the package to install the package.

## Configuration du formulaire adaptatif converti pour l’intégration de Forms Portal {#configure-converted-adaptive-form-for-forms-portal-integration}

Exécutez les étapes suivantes pour activer l’envoi de formulaires adaptatifs à l’aide de la page Forms Portal :
1. [Exécutez la conversion](convert-existing-forms-to-adaptive-forms.md#start-the-conversion-process) pour convertir un formulaire source en formulaire adaptatif.
1. Ouvrez le formulaire adaptatif en mode d’édition.
1. Appuyez sur Conteneur de formulaires et sélectionnez Configurer ![le formulaire](assets/configure-adaptive-form.png)adaptatif.
1. Dans la **[!UICONTROL Submission]** section, sélectionnez **[!UICONTROL Forms Portal Submit Action]** dans la liste **[!UICONTROL Submit Action]** déroulante.
1. Appuyez sur ![Enregistrer la stratégie](assets/edit_template_done.png) de modèle pour enregistrer les paramètres.

## Création et configuration de la page Forms Portal {#create-configure-forms-portal-page}

Effectuez les étapes suivantes pour créer une page Forms Portal et la configurer afin de pouvoir envoyer des formulaires adaptatifs à l’aide de cette page :

1. Connectez-vous à l’instance d’auteur AEM et appuyez sur **[!UICONTROL Adobe Experience Manager]** > **[!UICONTROL Sites]**.
1. Sélectionnez l’emplacement d’enregistrement de la nouvelle page Forms Portal et appuyez sur **[!UICONTROL Create]** > **[!UICONTROL Page]**.
1. Sélectionnez le modèle de la page, appuyez sur **[!UICONTROL Next]**, spécifiez un titre pour la page et appuyez sur **[!UICONTROL Create]**.
1. Appuyez sur **[!UICONTROL Edit]** pour configurer la page.
1. Dans l’en-tête de la page, appuyez sur ![Modifier le modèle](assets/edit_template_sites.png) > **[!UICONTROL Edit Template]** pour ouvrir le modèle de la page.
1. Appuyez sur Conteneur de mise en page et appuyez sur ![Modifier la stratégie](assets/edit_template_policy.png)de modèle. Dans l’ **[!UICONTROL Allowed Components]** onglet, activez les options **[!UICONTROL Document Services]** et **[!UICONTROL Document Services Predicates]** , puis appuyez sur ![Enregistrer la stratégie](assets/edit_template_done.png)de modèle.
1. Insérez le **[!UICONTROL Search & Lister]** composant dans la page. Par conséquent, tous les formulaires adaptatifs existants disponibles sur votre instance AEM sont répertoriés sur la page.
1. Insérez le **[!UICONTROL Drafts & Submissions]** composant dans la page. Deux onglets, **[!UICONTROL Draft Forms]** et **[!UICONTROL Submitted Forms]**, s’affichent sur la page Forms Portal. L’ **[!UICONTROL Draft Forms]** onglet affiche également le formulaire adaptatif converti généré à l’aide des étapes mentionnées dans [Configuration du formulaire adaptatif converti pour l’intégration de Forms Portal.](#configure-converted-adaptive-form-for-forms-portal-integration)

1. Appuyez sur **[!UICONTROL Preview]**, appuyez sur le formulaire adaptatif converti, spécifiez des valeurs pour les champs de formulaire adaptatif et envoyez-le. Les valeurs que vous spécifiez pour les champs de formulaire adaptatif sont envoyées à la base de données intégrée.
