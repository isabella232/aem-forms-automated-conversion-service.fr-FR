---
title: Envoyer les formulaires adaptatifs convertis avec un schéma JSON à la base de données
description: Envoyez les formulaires adaptatifs convertis avec un schéma JSON à la base de données en créant un modèle de données de formulaire et en y faisant référence dans un processus AEM.
uuid: f98b4cca-f0a3-4db8-aef2-39b8ae462628
topic-tags: forms
discoiquuid: cad72699-4a4b-4c52-88a5-217298490a7c
translation-type: tm+mt
source-git-commit: b879a0ddecd5370c754dfe9e1bf33121dd5ecc97

---


# Intégration d’un formulaire adaptatif à une base de données à l’aide du processus AEM {#submit-forms-to-database-using-forms-portal}

Le service de conversion automatisée de formulaires vous permet de convertir un formulaire PDF non interactif, un formulaire Acro ou un formulaire PDF XFA en formulaire adaptatif. Lors du lancement du processus de conversion, vous avez la possibilité de générer un formulaire adaptatif avec ou sans liaisons de données.

Si vous choisissez de générer un formulaire adaptatif sans liaison de données, vous pouvez intégrer le formulaire adaptatif converti à un modèle de données de formulaire, un schéma XML ou un schéma JSON après la conversion. Pour le modèle de données de formulaire, vous devez lier manuellement les champs de formulaire adaptatif au modèle de données de formulaire. Cependant, si vous générez un formulaire adaptatif avec des liaisons de données, le service de conversion associe automatiquement le ou les formulaires adaptatifs à un schéma JSON et crée une liaison de données entre les champs disponibles dans le formulaire adaptatif et le schéma JSON. Vous pouvez ensuite intégrer le formulaire adaptatif à une base de données de votre choix, remplir les données du formulaire et les envoyer à la base de données. De même, après une intégration réussie à la base de données, vous pouvez configurer les champs du formulaire adaptatif converti pour récupérer les valeurs de la base de données et préremplir les champs du formulaire adaptatif.

La figure suivante illustre les différentes étapes de l’intégration d’un formulaire adaptatif converti à une base de données :

![intégration de base de données](assets/integrate-adaptive-form-with-database.png)

Cet article décrit les instructions étape par étape pour exécuter toutes ces étapes d’intégration.

## Conditions préalables {#pre-requisites}

* Instance d’auteur AEM 6.5 avec la dernière version d’AEM 6.5 Service Pack
* Dernière version du module complémentaire AEM Forms
* [Service de conversion de formulaires automatisés](configure-service.md)
* Base de données à intégrer. La base de données utilisée dans l’exemple d’implémentation est MySQL 5.6.24. Vous pouvez toutefois intégrer le formulaire adaptatif converti à n’importe quelle base de données de votre choix.

## Exemple de formulaire adaptatif {#sample-adaptive-form}

Pour exécuter le cas d’utilisation afin d’intégrer des formulaires adaptatifs convertis à la base de données à l’aide d’un processus AEM, téléchargez l’exemple de fichier PDF suivant.

Vous pouvez télécharger l’exemple de formulaire Nous contacter à l’aide de :

[Obtenir le fichier](assets/sample_contact_us_form.pdf)

Le fichier PDF sert d’entrée au service de conversion automatisée des formulaires. Le service convertit ce fichier en formulaire adaptatif. L’image suivante illustre l’exemple de formulaire Nous contacter dans un format PDF.

![formulaire de demande de prêt](assets/sample_contact_us_form.png)

## Installez le fichier mysql-connector-java-5.1.39-bin.jar.{#install-mysql-connector-java-file}

Effectuez les étapes suivantes, sur toutes les instances d’auteur et de publication, pour installer le fichier mysql-connector-java-5.1.39-bin.jar :

1. Accédez au package com.mysql.jdbc `http://server:port/system/console/depfinder` et recherchez-le.
1. Dans la colonne Exporté par, vérifiez si le package est exporté par un groupe. Continuez si le package n’est pas exporté par un groupe.
1. Accédez à `http://server:port/system/console/bundles` et cliquez sur **[!UICONTROL Install/Update]**.
1. Click **[!UICONTROL Choose File]** and browse to select the mysql-connector-java-5.1.39-bin.jar file. Sélectionnez également **[!UICONTROL Start Bundle]** et **[!UICONTROL Refresh Packages]** cochez les cases.
1. Cliquez sur **[!UICONTROL Install]** ou **[!UICONTROL Update]**. Une fois cette opération effectuée, redémarrez le serveur.
1. (Windows uniquement) Désactivez le pare-feu système pour votre système d’exploitation.

## Préparation des données pour le modèle de formulaire {#prepare-data-for-form-model}

L’intégration de données AEM Forms permet de configurer des sources de données disparates et de s’y connecter. Après avoir généré un formulaire adaptatif à l’aide du processus de conversion, vous pouvez définir le modèle de formulaire en fonction d’un modèle de données de formulaire, d’un schéma XSD ou JSON. Vous pouvez utiliser une base de données, Microsoft Dynamics ou tout autre service tiers pour créer un modèle de données de formulaire.

Ce didacticiel utilise la base de données MySQL comme source pour créer un modèle de données de formulaire. Créez un schéma dans la base de données et ajoutez la table **de contacts** au schéma en fonction des champs disponibles dans le formulaire adaptatif.

![Exemple de données mysql](assets/db_entries_sample_form.png)

Vous pouvez utiliser l’instruction DDL suivante pour créer la table **contactus** dans la base de données.

```sql
CREATE TABLE `contactus` (
   `name` varchar(45) NOT NULL,
   `email` varchar(45) NOT NULL,
   `phonenumber` varchar(10) DEFAULT NULL,
   `issuedesc` varchar(1000) DEFAULT NULL,
   PRIMARY KEY (`email`)
 ) ENGINE=InnoDB DEFAULT CHARSET=utf8
```

## Configurer la connexion entre l’instance AEM et la base de données {#configure-connection-between-aem-instance-and-database}

Effectuez les étapes de configuration suivantes pour créer une connexion entre l’instance AEM et la base de données MYSQL :

1. Go to AEM Web Console Configuration page at `http://server:port/system/console/configMgr`.
1. Recherchez et cliquez pour ouvrir **[!UICONTROL Apache Sling Connection Pooled DataSource]** en mode d’édition dans la configuration de la console Web. Spécifiez les valeurs des propriétés comme décrit dans le tableau suivant :   

   <table> 
    <tbody> 
    <tr> 
    <th><strong>Propriétés</strong></th> 
    <th><strong>Valeur</strong></th> 
    </tr> 
    <tr> 
    <td><p>Nom de la source de données </p></td> 
    <td><p>Un nom de source de données pour filtrer les pilotes du pool de la source de données .</p></td>
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

## Créer un modèle de données de formulaire {#create-form-data-model}

Une fois que vous avez configuré MYSQL en tant que source de données, exécutez les étapes suivantes pour créer un modèle de données de formulaire :

1. Dans l’instance d’auteur AEM, accédez à **[!UICONTROL Forms]** > **[!UICONTROL Data Integrations]**.

1. Appuyer **[!UICONTROL Create]** > **[!UICONTROL Form Data Model]**.

1. Dans l’ **[!UICONTROL Create Form Data Model]** assistant, spécifiez **workflow_submit** comme nom du modèle de données de formulaire. Appuyer **[!UICONTROL Next]**.

1. Sélectionnez la source de données MYSQL que vous avez configurée dans la section précédente et appuyez sur **[!UICONTROL Create]**.

1. Appuyez sur **[!UICONTROL Edit]** et développez la source de données répertoriée dans le volet de gauche pour sélectionner la table de **contacts** , **[!UICONTROL get]** les services et les **[!UICONTROL insert]** services, puis appuyez sur **[!UICONTROL Add Selected]**.

   ![Exemple de données mysql](assets/fdm_details_workfdlow_submit.png)

1. Sélectionnez l’objet de modèle de données dans le volet de droite et appuyez sur **[!UICONTROL Edit Properties]**. Sélectionnez **[!UICONTROL get]** et **[!UICONTROL insert]** dans les listes **[!UICONTROL Read Service]** et **[!UICONTROL Write Service]** déroulantes. Spécifiez les arguments du service de lecture et appuyez sur **[!UICONTROL Done]**.

1. Dans l’ **[!UICONTROL Services]** onglet, sélectionnez le **[!UICONTROL get]** service et appuyez sur **[!UICONTROL Edit Properties]**. Sélectionnez le **[!UICONTROL Output Model Object]**, désactivez la **[!UICONTROL Return array]** bascule et appuyez sur **[!UICONTROL Done]**.

1. Select the **[!UICONTROL Insert]** service and tap **[!UICONTROL Edit Properties]**. Select the **[!UICONTROL Input Model Object]** and tap **[!UICONTROL Done]**.

1. Tap **[!UICONTROL Save]** to save the form data model.

Vous pouvez télécharger l’exemple de modèle de données de formulaire à l’aide de :

[Obtenir le fichier](assets/DownloadedFormsPackage_1497728018502500.zip)

## Générer des formulaires adaptatifs avec liaison JSON {#generate-adaptive-forms-with-json-binding}

Utilisez le service de conversion [automatisée des formulaires pour convertir](convert-existing-forms-to-adaptive-forms.md) le formulaire [Nous](#sample-adaptive-form) contacter en formulaire adaptatif avec liaison de données. Veillez à ne pas cocher la **[!UICONTROL Generate adaptive form(s) without data bindings]** case lors de la génération du formulaire adaptatif.

![Formulaire adaptatif avec liaison JSON](assets/generate_af_with_data_bindings.png)

Sélectionnez le formulaire **** Nous contacter converti disponible dans le **[!UICONTROL output]** dossier **[!UICONTROL Forms & Documents]** et appuyez sur **[!UICONTROL Edit]**. Appuyez sur **[!UICONTROL Preview]**, saisissez des valeurs dans les champs du formulaire adaptatif et appuyez sur **[!UICONTROL Submit]**.

Connectez-vous à **crx-repository** et accédez à */content/forms/fp/admin/submit/data* pour afficher les valeurs envoyées au format JSON. Voici les exemples de données au format JSON lorsque vous envoyez le formulaire adaptatif **Contactez-nous** converti :

```json
{
  "afData": {
    "afUnboundData": {
      "data": {}
    },
    "afBoundData": {
      "data": {
        "name1": "Gloria",
        "email": "abc@xyz.com",
        "phone_number": "2346578965",
        "issue_description": "Test message"
      }
    },
    "afSubmissionInfo": {
      "computedMetaInfo": {},
      "stateOverrides": {},
      "signers": {},
      "afPath": "/content/dam/formsanddocuments/docs_conversion/output/sample_form_json",
      "afSubmissionTime": "20191204014007"
    }
  }
}
```

Vous devez maintenant créer un modèle de flux de travail capable de traiter ces données et de les envoyer à la base de données MYSQL à l’aide du modèle de données de formulaire que vous avez créé dans les sections précédentes.

## Création d’un modèle de processus pour traiter les données JSON {#create-workflow-model}

Exécutez les étapes suivantes pour créer un modèle de processus afin d’envoyer les données de formulaire adaptatif à la base de données :

1. Ouvrez la console Modèles de processus. L’URL par défaut est `https://server:port/libs/cq/workflow/admin/console/content/models.html/etc/workflow/models`.

1. Sélectionnez **[!UICONTROL Create]**, puis **[!UICONTROL Create Model]**. The **[!UICONTROL Add Workflow Model]** dialog appears.

1. Saisissez les champs **[!UICONTROL Title]** et **[!UICONTROL Name]** (facultatif). Par exemple, **workflow_json_submit**. Appuyez **[!UICONTROL Done]** sur pour créer le modèle.

1. Sélectionnez le modèle de processus et appuyez sur **[!UICONTROL Edit]** pour ouvrir le modèle en mode d’édition. Appuyez sur + et ajoutez **[!UICONTROL Invoke Form Data Model Service]** une étape au modèle de processus.

1. Appuyez sur l’ **[!UICONTROL Invoke Form Data Model Service]** étape et appuyez sur ![Configurer](assets/configure_icon.png).

1. Dans l’ **[!UICONTROL Form Data Model]** onglet, sélectionnez le modèle de données de formulaire que vous avez créé dans le **[!UICONTROL Form Data Model path]** champ et sélectionnez **[!UICONTROL insert]** dans la liste **[!UICONTROL Service]** déroulante.

1. Dans l’ **[!UICONTROL Input for Service]** onglet, sélectionnez **[!UICONTROL Provide input data using literal, variable, or a workflow metadata, and a JSON file]** dans la liste déroulante, cochez la **[!UICONTROL Map input fields from input JSON]** case, sélectionnez **[!UICONTROL Relative to payload]** et indiquez **data.xml** comme valeur du **[!UICONTROL Select input JSON document using]** champ.

1. Dans la **[!UICONTROL Service Arguments]** section, indiquez les valeurs suivantes pour les arguments de modèle de données de formulaire :

   ![Invoquer service de modèle de données de formul.](assets/invoke_form_data_model_service.png)

   Notez que les champs du modèle de données de formulaire, par exemple, contactus dot name, sont mappés à **afData.afBoundData.data.name1**, qui fait référence aux liaisons de schéma JSON pour le formulaire adaptatif envoyé.

## Configuration de l’envoi de formulaire adaptatif {#configure-adaptive-form-submission}

Exécutez les étapes suivantes pour envoyer le formulaire adaptatif au modèle de processus que vous avez créé dans la section précédente :

1. Sélectionnez le formulaire Nous contacter converti disponible dans le **[!UICONTROL output]** dossier **[!UICONTROL Forms & Documents]** et appuyez sur **[!UICONTROL Edit]**.

1. Ouvrez les propriétés du formulaire adaptatif en appuyant sur **[!UICONTROL Form Container]** puis sur ![Configurer](assets/configure_icon.png).

1. Dans la **[!UICONTROL Submission]** section, sélectionnez **[!UICONTROL Invoke an AEM workflow]** dans la liste **[!UICONTROL Submit Action]** déroulante, sélectionnez le modèle de flux de travail que vous avez créé dans la section précédente, puis spécifiez **data.xml** dans le **[!UICONTROL Data File Path]** champ.

1. Appuyez sur ![Enregistrer](assets/save_icon.png) pour enregistrer les propriétés.

1. Appuyez sur **[!UICONTROL Preview]**, saisissez des valeurs dans les champs du formulaire adaptatif et appuyez sur **[!UICONTROL Submit]**. Les valeurs envoyées s’affichent désormais dans la table de base de données MYSQL au lieu de **crx-repository**.

## Configuration d’un formulaire adaptatif pour préremplir les valeurs de la base de données

Exécutez les étapes suivantes pour configurer le formulaire adaptatif afin de préremplir les valeurs de la base de données MYSQL en fonction de la clé principale définie dans le tableau (Courriel dans ce cas) :

1. Appuyez sur le champ **E-mail** dans le formulaire adaptatif et appuyez sur ![Modifier la règle](assets/edit-rules.png).

1. Appuyez sur **[!UICONTROL Create]** puis sélectionnez **[!UICONTROL is changed]** dans la liste **[!UICONTROL Select State]** déroulante de la **[!UICONTROL When]** section.

1. Dans la **[!UICONTROL Then]** section, sélectionnez **[!UICONTROL Invoke Service]** et **obtenez** le service du modèle de données de formulaire que vous avez créé dans une section précédente de cet article.

1. Sélectionnez **E-mail** dans la **[!UICONTROL Input]** section et les trois autres champs du modèle de données de formulaire, **Nom**, Numéro **** de téléphone et Description de la publication dans la section . ******[!UICONTROL Output]** Tap **[!UICONTROL Done]** to save the settings.

   ![Configuration des paramètres de préremplissage de courrier électronique](assets/email_prefill_settings.png)

   En conséquence, en fonction des entrées de courrier électronique existantes dans la base de données MYSQL, vous pouvez préremplir les valeurs des trois autres champs en mode **[!UICONTROL Preview]** du formulaire adaptatif. Si, par exemple, vous indiquez aya.tan@xyz.com dans le champ **E-mail** (en fonction des données existantes dans la section [Préparer le modèle](#prepare-data-for-form-model) de données de formulaire de cet article) et que vous sortez du champ, les trois autres champs, **Nom**, Numéro **de téléphone et Description s’affichent automatiquement dans le formulaire adaptatif.******

Vous pouvez télécharger l’exemple de formulaire adaptatif converti à l’aide de :

[Obtenir le fichier](assets/DownloadedFormsPackage_1498226829041200.zip)
