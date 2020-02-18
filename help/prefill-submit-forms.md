---
title: Processus de préremplissage et d’envoi recommandés basés sur la source de données pour les formulaires adaptatifs
seo-title: Options de préremplissage et d’envoi pour les formulaires adaptatifs
description: Processus de préremplissage et d’envoi basés sur la source de données pour les formulaires adaptatifs générés à l’aide du service de conversion automatisée des formulaires.
seo-description: Processus de préremplissage et d’envoi basés sur la source de données pour les formulaires adaptatifs générés à l’aide du service de conversion automatisée des formulaires.
uuid: 91409a82-141c-4233-82b1-1539a0b250f8
contentOwner: khsingh
topic-tags: forms
discoiquuid: cad34fff-7f9f-4a27-8b5c-d0a523903eec
privatebeta: true
translation-type: tm+mt
source-git-commit: f598871fd41c402f98d94d7b2174ab8b2e487075

---


# Processus de préremplissage et d’envoi recommandés basés sur la source de données pour les formulaires adaptatifs {#recommended-data-source-btased-prefill-and-submit-workflows-for-adaptive-forms}

Vous pouvez utiliser l’une des sources de données suivantes avec des formulaires adaptatifs convertis à l’aide du service de conversion automatisée de formulaires :

* Modèle de données de formulaire, OData ou tout autre service tiers
* Schéma JSON
* Schéma XSD

Selon la source de données, vous pouvez choisir de générer un formulaire adaptatif avec ou sans modèle de données.

Cet article décrit les processus recommandés pour préremplir les valeurs de champ et les options d’envoi après avoir sélectionné une source de données et généré un formulaire adaptatif à l’aide du service de conversion.

<table> 
 <tbody> 
  <tr> 
   <th><strong>Source de données</strong></th> 
   <th><strong>Processus recommandé</strong></th> 
  </tr> 
  <tr> 
   <td><p>Modèle de données de formulaire, OData ou tout autre service tiers</p></td> 
   <td> 
    <p><strong>Option 1</strong>: Vous sélectionnez le modèle de données de formulaire, OData ou tout autre service tiers comme source de données. Vous <a href="#generate-adaptive-forms-with-no-data-binding">générez un formulaire adaptatif sans liaison</a> de données à l’aide du service de conversion automatisée des formulaires. Vous liez manuellement les champs du formulaire adaptatif aux entités du modèle de données de formulaire et utilisez l’option Service de préremplissage du modèle de données de formulaire pour préremplir les valeurs des champs. Utilisez l’option Envoyer à l’aide du modèle de données de formulaire pour envoyer le formulaire adaptatif.</p></td> 
  </tr>
  <tr> 
   <td></td> 
   <td> 
   <p><strong>Option 2</strong>: Vous sélectionnez le modèle de données de formulaire, OData ou tout autre service tiers comme source de données. Vous <a href="#generate-adaptive-forms-with-no-data-binding">générez un formulaire adaptatif sans liaison</a> de données à l’aide du service de conversion automatisée des formulaires. Vous liez les champs du formulaire adaptatif à l’aide de l’éditeur de règles pour préremplir les valeurs de champ. Modifiez les valeurs de champ, si nécessaire, et envoyez les données au répertoire crx-repository.</p>
    </td> 
  </tr>
  <tr> 
   <td></td> 
   <td> 
    <p>Pour obtenir des instructions détaillées sur l’exécution de ces processus, voir <a href="#sqldatasource">Utilisation de la base de données, d’OData ou de tout service tiers en tant que source de données.</a></p> </td> 
  </tr>
  <tr>
  <td><p>Schéma JSON</p></td> 
   <td> 
    <p>Vous sélectionnez le schéma JSON comme source de données. Basé sur la source de données sélectionnée :</p></td> 
  </tr>
  <tr>
  <td></td> 
   <td> 
    <p><strong>Option 1</strong>: Vous <a href="#generate-adaptive-forms-with-no-data-binding">générez un formulaire adaptatif sans liaison</a> de données à l’aide du service de conversion automatisée des formulaires et configurez le schéma JSON en tant que source de données. Vous liez manuellement les champs du formulaire adaptatif au schéma JSON et vous <a href="https://helpx.adobe.com/experience-manager/6-5/forms/using/prepopulate-adaptive-form-fields.html#Supportedprotocolsforprefillinguserdata" target="_blank">utilisez l’un des protocoles</a> pris en charge pour préremplir les valeurs de champ. Modifiez les valeurs de champ, si nécessaire, et envoyez les données au répertoire crx-repository.</p></td> 
  </tr>
  <tr>
  <td></td> 
   <td> 
    <p>Pour obtenir des instructions détaillées sur l’exécution des processus, voir <a href="#jsondatasource">Utilisation du schéma JSON comme source de données.</p></td> 
  </tr>
  <tr>
  <td></td> 
   <td> 
    <p><strong>Option 2</strong>: Vous <a href="#generate-adaptive-forms-with-json-binding">générez un formulaire adaptatif avec liaison</a> de données JSON à l’aide du service de conversion automatisée des formulaires. Le service de préremplissage et la fonction d’envoi de formulaire fonctionnent de manière transparente. Vous n’avez pas besoin d’étapes de configuration.</p> </td> 
  </tr>
   <tr>
  <td></td> 
   <td> 
    <p>Pour obtenir des instructions détaillées sur l’exécution des processus, voir <a href="#jsonwithdatabinding">Utilisation du schéma JSON comme source de données.</a></p> </td> 
  </tr>
  <tr>
  <td><p>Schéma XSD</p></td> 
   <td> 
    <p>Vous sélectionnez le schéma XSD comme source de données. En fonction de la source de données sélectionnée, vous <a href="#generate-adaptive-forms-with-no-data-binding">générez un formulaire adaptatif sans liaison</a> de données à l’aide du service de conversion automatisée des formulaires et vous configurez le schéma XSD comme source de données. Vous liez manuellement les champs du formulaire adaptatif au schéma XSD et vous <a href="https://helpx.adobe.com/experience-manager/6-5/forms/using/prepopulate-adaptive-form-fields.html#Supportedprotocolsforprefillinguserdata" target="_blank">utilisez l’un des protocoles</a> pris en charge pour préremplir les valeurs de champ. Modifiez les valeurs de champ, si nécessaire, et envoyez les données au répertoire crx-repository.</p>
    </td> 
  </tr>
  <tr>
  <td></td> 
   <td> 
    <p>Pour obtenir des instructions détaillées sur l’exécution des processus, voir <a href="#xsddatasource">Utilisation du schéma XSD comme source de données.</a></p>
    </td> 
  </tr>
 </tbody> 
</table>


Pour plus d’informations sur le service de conversion automatisée des formulaires, voir les articles suivants :

* [Présentation du service de conversion automatisée des formulaires](introduction.md)
* [Configuration du service de conversion de formulaires automatisés](configure-service.md)
* [Conversion de formulaires d’impression en formulaires adaptatifs](convert-existing-forms-to-adaptive-forms.md)
* [Vérification et correction des formulaires convertis](review-correct-ui-edited.md)

Les informations fournies dans cet article partent du principe que quiconque le lit possède une connaissance de base des concepts de formulaires adaptatifs.

## Conditions préalables {#pre-requisites}

* Configure an [AEM author instance](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/deploy.html)
* Configuration du service de conversion [automatisée des formulaires sur l’instance d’auteur AEM](configure-service.md)

## Exemple de formulaire adaptatif {#sample-adaptive-form}

Pour exécuter les cas d’utilisation de préremplissage des valeurs de champ dans un formulaire adaptatif et les envoyer à la source de données, téléchargez l’exemple de fichier PDF suivant.

Exemple de formulaire de demande de prêt

[Obtenir le fichier](assets/sample_loan_application_form.pdf)

Le fichier PDF sert d’entrée au service de conversion automatisée des formulaires. Le service convertit ce fichier en formulaire adaptatif. L’image suivante illustre l’exemple de demande de prêt au format PDF.

![formulaire de demande de prêt](assets/sample_form_new.png)

## Préparation des données pour le modèle de formulaire {#prepare-data-for-form-model}

L’intégration de données AEM Forms permet de configurer des sources de données disparates et de s’y connecter. Après avoir généré un formulaire adaptatif à l’aide du processus de conversion, vous pouvez définir le modèle de formulaire en fonction d’un modèle de données de formulaire, d’un schéma XSD ou JSON. Vous pouvez utiliser une base de données, Microsoft Dynamics ou tout autre service tiers pour créer un modèle de données de formulaire.

Ce didacticiel utilise la base de données MySQL comme source pour créer un modèle de données de formulaire. Créez un schéma d’application de **prêt** dans la base de données et ajoutez une table de **demandeur** au schéma en fonction des champs disponibles dans le formulaire adaptatif.

![Exemple de données mysql](assets/sample_data_mysql.png)

Vous pouvez utiliser l’instruction DDL suivante pour créer la table **candidat** dans la base de données.

```sql
CREATE TABLE `applicant` (
   `name` varchar(45) DEFAULT NULL,
   `address` varchar(45) DEFAULT NULL,
   `phonenumber` int(11) NOT NULL,
   `email` varchar(45) DEFAULT NULL,
   `occupation` varchar(45) DEFAULT NULL,
   `annualsalary` varchar(45) DEFAULT NULL,
   `familymembers` int(11) DEFAULT NULL,
   PRIMARY KEY (`phonenumber`)
 ) ENGINE=InnoDB DEFAULT CHARSET=utf8
```

Si vous utilisez un schéma XSD comme modèle de formulaire pour exécuter les cas d’utilisation, créez un fichier XSD avec le texte suivant :

```xml
<?xml version="1.0" encoding="utf-8" ?>
    <xs:schema targetNamespace="http://adobe.com/sample.xsd"
                    xmlns="http://adobe.com/sample.xsd"
                    xmlns:xs="http://www.w3.org/2001/XMLSchema">

<xs:element name="sample" type="SampleType"/>

  <xs:complexType name="SampleType">
    <xs:sequence>
      <xs:element name="name" type="xs:string"/>
   <xs:element name="address" type="xs:string"/>
   <xs:element name="phonenumber" type="xs:int"/>
   <xs:element name="email" type="xs:string"/>
   <xs:element name="occupation" type="xs:string"/>
   <xs:element name="annualsalary" type="xs:string"/>
   <xs:element name="familymembers" type="xs:string"/>
 </xs:sequence>
  </xs:complexType>

  </xs:schema>
```

Ou téléchargez le schéma XSD sur le système de fichiers local.

Exemple de schéma XSD de demande de prêt

[Obtenir le fichier](assets/loanapplication.xsd)

Pour plus d’informations sur l’utilisation du schéma XSD comme modèle de formulaire dans les formulaires adaptatifs, voir [Création de formulaires adaptatifs à l’aide du schéma](https://helpx.adobe.com/experience-manager/6-5/forms/using/adaptive-form-xml-schema-form-model.html)XML.

Si vous utilisez un schéma JSON comme modèle de formulaire pour exécuter les cas d’utilisation, créez un fichier JSON avec le texte suivant :

```JSON
{
    "$schema": "http://json-schema.org/draft-04/schema#",
    "definitions": {
        "loanapplication": {
            "type": "object",
            "properties": {
                "name": {
                    "type": "string"
                },
                "address": {
                    "type": "string"
                },
    "phonenumber": {
                    "type": "number"
                },
    "email": {
                    "type": "string"
                },
    "occupation": {
                    "type": "string"
                },
    "annualsalary": {
                    "type": "string"
                },
    "familymembers": {
                    "type": "number"
                }
            }
        }
 },
 "type": "object",
    "properties": {
        "employee": {
            "$ref": "#/definitions/loanapplication"
        }
    }
}
```

Ou téléchargez le schéma JSON sur le système de fichiers local.

Exemple de schéma JSON de demande de prêt

[Obtenir le fichier](assets/demo_schema.json)

Pour plus d’informations sur l’utilisation du schéma JSON comme modèle de formulaire dans les formulaires adaptatifs, voir [Création de formulaires adaptatifs à l’aide du schéma](https://helpx.adobe.com/experience-manager/6-5/forms/using/adaptive-form-json-schema-form-model.html)JSON.

## Générer des formulaires adaptatifs sans liaison de données {#generate-adaptive-forms-with-no-data-binding}

Utilisez le service de conversion [automatisée de formulaires pour convertir](convert-existing-forms-to-adaptive-forms.md) l’ [exemple de formulaire](#sample-adaptive-form) de demande de prêt en formulaire adaptatif sans liaison de données. Veillez à cocher la **[!UICONTROL Generate adaptive form(s) without data bindings]** case pour générer le formulaire adaptatif sans liaison de données.

![Formulaire adaptatif sans liaison de données](assets/generate_af_without_binding.png)

Après avoir généré un formulaire adaptatif sans liaison de données, sélectionnez une source de données pour le formulaire adaptatif :

* [Base de données, OData ou tout service tiers](#sqldatasource)
* [Schéma JSON](#jsondatasource)
* [Schéma XSD](#xsddatasource)

>[!NOTE]
> Si le formulaire adaptatif que vous convertissez à l’aide du service de conversion automatisée des formulaires contient plusieurs champs portant le même nom, assurez-vous que ces champs sont liés à des entités de source de données afin d’éviter une perte de données possible lors de l’envoi.


### Utiliser la base de données, OData ou tout service tiers comme source de données {#sqldatasource}

Cas d’utilisation : Vous générez un formulaire adaptatif sans liaison de données à l’aide du service de conversion automatisée des formulaires et configurez la base de données MYSQL en tant que source de données. Vous liez manuellement les champs du formulaire adaptatif aux entités du modèle de données et utilisez l’ **[!UICONTROL Form Data Model Prefill Service]** option pour préremplir les valeurs de champ. Utilisez cette **[!UICONTROL Submit using Form Data Model]** option pour envoyer le formulaire adaptatif.

Avant d’exécuter le cas d’utilisation :

* [Configuration de la base de données MySQL en tant que source de données](https://helpx.adobe.com/experience-manager/6-5/forms/using/configure-data-sources.html#configurerelationaldatabase)
* [Création du modèle de données de formulaire](https://helpx.adobe.com/experience-manager/6-5/forms/using/work-with-form-data-model.html)

En fonction du cas d’utilisation, créez le modèle de données de formulaire de **demande** de prêt et liez l’argument de service de lecture à une **[!UICONTROL Literal]** valeur. La valeur littérale du numéro de téléphone doit correspondre à l’un des enregistrements configurés dans le schéma **demandeur** de la base de données MySQL. Les services utilisent la valeur comme argument pour récupérer les détails de la source de données. Vous pouvez également sélectionner Attribut de profil [utilisateur ou Attribut](https://helpx.adobe.com/experience-manager/6-5/forms/using/work-with-form-data-model.html#bindargument) de requête dans la liste **[!UICONTROL Binding To]** déroulante.

![Configurer un modèle de données de formulaire](assets/configure_model_object.png)

>[!NOTE]
>
>Veillez à ajouter des services **get** et **insert** au modèle de données de formulaire, à configurer et à tester les services avant d’exécuter le cas d’utilisation.

Exécutez les étapes suivantes :

1. Sélectionnez l’ **exemple converti de formulaire** de demande de prêt disponible dans le **[!UICONTROL output]** dossier et appuyez sur **[!UICONTROL Properties]**.
1. Appuyez sur l’ **[!UICONTROL Form Model]** onglet, sélectionnez **[!UICONTROL Form Data Model]** dans la liste **[!UICONTROL Select From]** déroulante et appuyez **[!UICONTROL Select Form Data Model]** sur pour sélectionner le modèle de données de formulaire de demande de **prêt** . Tap **[!UICONTROL Save & Close]** to save the form.
1. Sélectionnez l’ **exemple de formulaire** de demande de prêt et appuyez sur **[!UICONTROL Edit]**.
1. Dans l’ **[!UICONTROL Content]** onglet, appuyez sur l’icône Configurer :

   ![configurer le conteneur de formulaires](assets/configure_form_container.png)

   1. Dans la **[!UICONTROL Basic]** section, sélectionnez **[!UICONTROL Form Data Model Prefill service]** dans la liste **[!UICONTROL Prefill Service]** déroulante.

   1. Dans la **[!UICONTROL Submission]** section, sélectionnez **[!UICONTROL Submit using Form Data Model]** dans la liste **[!UICONTROL Submit Action]** déroulante.

   1. Sélectionnez le modèle de données à l’aide du **[!UICONTROL Data Model to submit]** champ.
   1. Tap ![done icon](https://helpx.adobe.com/content/dam/help/en/experience-manager/6-4/forms/using/chart-component/Done_Icon.png) to save the properties.

1. Appuyez sur la zone de texte Nom du demandeur et sélectionnez ![Configurer l’icône](https://helpx.adobe.com/content/dam/help/en/experience-manager/6-4/forms/using/configure_icon.png) (Configurer).

   1. Dans le champ Référence de liaison, sélectionnez **Demandeur** > **Nom**, puis appuyez sur l’icône ![](https://helpx.adobe.com/content/dam/help/en/experience-manager/6-4/forms/using/chart-component/Done_Icon.png) Terminé pour enregistrer les propriétés. De même, créez une liaison de données pour l’ **adresse**, le numéro **de** téléphone, le **courriel**, le métier, le salaire annuel  (en dollars) et le **numéro d’.********des champs des membres** de famille dépendants avec les entités du modèle de données de formulaire.
   ![Liaison de références](assets/bind_references.png)

1. Appuyez sur **[!UICONTROL Preview]** pour afficher les valeurs préremplies de champ de formulaire adaptatif.
1. Si nécessaire, modifiez les valeurs de champ et envoyez le formulaire adaptatif. Les valeurs de champ sont envoyées à la base de données MySQL. Vous pouvez actualiser la table **du demandeur** dans la base de données pour afficher les valeurs mises à jour dans la table.

**** Cas d’utilisation : Vous générez un formulaire adaptatif sans liaison de données à l’aide du service de conversion automatisée des formulaires et configurez la base de données MYSQL en tant que source de données. Vous liez les champs du formulaire adaptatif à l’aide de l’éditeur de règles pour préremplir les valeurs de champ. Modifiez les valeurs de champ, si nécessaire, et envoyez les données au répertoire crx-repository.

Exécutez les étapes suivantes pour utiliser l’éditeur [de](https://helpx.adobe.com/experience-manager/6-5/forms/using/rule-editor.html) règles afin d’appeler le service de modèle de données de formulaire pour lier des champs et des valeurs de préremplissage dans un formulaire adaptatif :

1. Sélectionnez l’ **exemple de formulaire** de demande de prêt dans le **[!UICONTROL output]** dossier et appuyez sur **[!UICONTROL Edit]**.
1. Dans l’ **[!UICONTROL Content]** onglet, appuyez sur l’icône Configurer :

   ![configurer le conteneur de formulaires](assets/configure_form_container.png)

   Dans la **[!UICONTROL Basic]** section, sélectionnez **[!UICONTROL Form Data Model Prefill service]** dans la liste **[!UICONTROL Prefill Service]** déroulante.

1. Appuyez sur la **[!UICONTROL Applicant Name]** zone de texte et appuyez sur **[!UICONTROL Edit Rules]**.

   ![Modifier les règles pour créer une liaison de données](assets/edit_rules_bind_reference.png)

1. Appuyez **[!UICONTROL Create]** sur la page Editeur de règles.
1. Sur la **[!UICONTROL Rule Editor]** page :

   1. Sélectionnez un état pour la zone de texte Nom du demandeur. Par exemple, **[!UICONTROL is initialized]**, ce qui entraîne l’exécution de la **[!UICONTROL Then]** condition lorsque vous générez le formulaire en **[!UICONTROL Preview]** mode.

   1. Dans la **[!UICONTROL Then]** section, sélectionnez **[!UICONTROL Invoke Service]** dans la liste **[!UICONTROL Select Action]** déroulante. Tous les services de votre instance Forms s’affichent dans la liste déroulante.

   1. Sélectionnez un **[!UICONTROL Get]** service dans la section répertoriant les modèles de données de formulaire. Le champ Input affiche **le numéro** de téléphone, qui est la clé principale définie pour le modèle de données **demandeur** . Le système récupère et préremplit les valeurs du formulaire adaptatif pour les champs de la section Sortie en fonction de ce champ.

   1. Créez une liaison pour les champs du formulaire adaptatif avec les entités du modèle de données de formulaire à l’aide de la section Sortie. Par exemple, liez le champ du formulaire **[!UICONTROL Applicant Name]** adaptatif à l’entité **name** .

   1. Appuyer **[!UICONTROL Done]**. Appuyez de **[!UICONTROL Done]** nouveau sur la page Editeur de règles.
   ![Editeur de règles pour lier des références](assets/rule_editor_bind_references.png)

1. Appuyez sur **[!UICONTROL Preview]** pour afficher les valeurs préremplies de champ de formulaire adaptatif.

   >[!NOTE]
   >
   >Assurez-vous que la propriété **[!UICONTROL Return Array]** est définie sur OFF pour la propriété de service **get** dans le modèle de données de formulaire associé au formulaire adaptatif.

1. Si nécessaire, modifiez les valeurs de champ et envoyez le formulaire adaptatif. Les données envoyées sont disponibles à l’emplacement suivant dans le référentiel crx :

   `http://host name:port/crx/de/index.jsp#/content/forms/fp/admin/submit/data/latest file available in the folder`

### Utiliser le schéma JSON comme source de données {#jsondatasource}

**** Cas d’utilisation : Vous générez un formulaire adaptatif sans liaison de données à l’aide du service de conversion automatisée des formulaires et configurez le schéma JSON comme source de données. Vous liez manuellement les champs du formulaire adaptatif au schéma JSON et utilisez l’option **Aperçu avec données** pour préremplir les valeurs de champ. Modifiez les valeurs de champ, si nécessaire, et envoyez les données au répertoire crx-repository.

Avant d’exécuter le cas d’utilisation, vérifiez que vous disposez des éléments suivants :

* [un schéma JSON valide conforme à la structure du schéma JSON](#prepare-data-for-form-model)
* [un formulaire adaptatif sans liaison de données](#generate-adaptive-forms-with-no-data-binding)

Exécutez les étapes suivantes :

1. Sélectionnez l’ **exemple converti de formulaire** de demande de prêt disponible dans le dossier de **sortie** et appuyez sur **[!UICONTROL Properties]**.
1. Appuyez sur l’ **[!UICONTROL Form Model]** onglet, sélectionnez **[!UICONTROL Schema]** dans la liste **[!UICONTROL Select From]** déroulante, puis appuyez **[!UICONTROL Select Schema]** pour télécharger le schéma JSON **** demo.schema enregistré sur le système de fichiers local. Tap **[!UICONTROL Save & Close]** to save the form.
1. Sélectionnez l’ **exemple de formulaire** de demande de prêt et appuyez sur **[!UICONTROL Edit]**.
1. Appuyez sur la zone de texte Nom du demandeur et sélectionnez ![Configurer l’icône](https://helpx.adobe.com/content/dam/help/en/experience-manager/6-4/forms/using/configure_icon.png) (Configurer).

   Dans le champ Référence de liaison, sélectionnez **Demandeur** > **Nom**, puis appuyez sur l’icône ![](https://helpx.adobe.com/content/dam/help/en/experience-manager/6-4/forms/using/chart-component/Done_Icon.png) Terminé pour enregistrer les propriétés. De même, créez une liaison de données pour l’ **adresse**, le numéro **de** téléphone, le **courriel**, le métier, le salaire annuel  (en dollars) et le **numéro d’.********des champs des membres** de famille dépendants avec les entités de schéma JSON.

1. Sélectionnez à nouveau l’ **exemple de formulaire** de demande de prêt converti disponible dans le **[!UICONTROL output]** dossier et sélectionnez **[!UICONTROL Preview]** > **[!UICONTROL Preview with Data]**.</br>

   Télécharger le fichier de données d’exemple</br>

   [Obtenir le fichier](assets/json_data_file.txt)</br>

1. Si nécessaire, modifiez les valeurs de champ et envoyez le formulaire adaptatif. Les données envoyées sont disponibles à l’emplacement suivant dans le référentiel crx :

   `http://host name:port/crx/de/index.jsp#/content/forms/fp/admin/submit/data/latest file available in the folder`

### Utiliser le schéma XSD comme source de données {#xsddatasource}

**** Cas d’utilisation : Vous générez un formulaire adaptatif sans liaison de données à l’aide du service de conversion automatisée des formulaires et configurez le schéma XSD en tant que source de données. Vous liez manuellement les champs du formulaire adaptatif au schéma XSD et utilisez l’ **aperçu avec des données** pour préremplir les valeurs de champ. Modifiez les valeurs de champ, si nécessaire, et envoyez les données au répertoire crx-repository.

Avant d’exécuter le cas d’utilisation, vérifiez que vous disposez des éléments suivants :

* [un schéma XSD valide conforme à la structure du schéma XML](#prepare-data-for-form-model)
* [un formulaire adaptatif sans liaison de données](#generate-adaptive-forms-with-no-data-binding)

Exécutez les étapes suivantes :

1. Sélectionnez l’ **exemple converti de formulaire** de demande de prêt disponible dans le **[!UICONTROL output]** dossier et appuyez sur **[!UICONTROL Properties]**.
1. Appuyez sur l’ **[!UICONTROL Form Model]** onglet, sélectionnez **[!UICONTROL Schema]** dans la liste **[!UICONTROL Select From]** déroulante, puis appuyez **[!UICONTROL Select Schema]** pour télécharger le schéma XSD de l’application de **** prêt enregistré sur le système de fichiers local. Sélectionnez l’élément racine pour le schéma XSD et appuyez **[!UICONTROL Save & Close]** sur pour enregistrer le formulaire.
1. Sélectionnez l’ **exemple de formulaire** de demande de prêt et appuyez sur **[!UICONTROL Edit]**.
1. Appuyez sur la zone de texte Nom du demandeur et sélectionnez ![Configurer l’icône](https://helpx.adobe.com/content/dam/help/en/experience-manager/6-4/forms/using/configure_icon.png) (Configurer).
Dans le champ Référence de liaison, sélectionnez **Demandeur** > **Nom**, puis appuyez sur l’icône ![](https://helpx.adobe.com/content/dam/help/en/experience-manager/6-4/forms/using/chart-component/Done_Icon.png) Terminé pour enregistrer les propriétés. De même, créez une liaison de données pour l’ **adresse**, le numéro **de** téléphone, le **courriel**, le métier, le salaire annuel  (en dollars) et le **numéro d’.********des champs des membres** de famille dépendants avec les entités de schéma XSD.

1. Sélectionnez à nouveau l’ **exemple de formulaire** de demande de prêt converti disponible dans le dossier de **sortie** et sélectionnez **[!UICONTROL Preview]** > **[!UICONTROL Preview with Data]**.</br>

   Télécharger le fichier de données d’exemple</br>

   [Obtenir le fichier](assets/loan-application-data-xml-data.zip)</br>


1. Si nécessaire, modifiez les valeurs de champ et envoyez le formulaire adaptatif. Les données envoyées sont disponibles à l’emplacement suivant dans le référentiel crx :

   `http://host name:port/crx/de/index.jsp#/content/forms/fp/admin/submit/data/latest file available in the folder`

## Générer des formulaires adaptatifs avec liaison JSON {#generate-adaptive-forms-with-json-binding}

Utilisez le service de conversion [automatisée de formulaires pour convertir](convert-existing-forms-to-adaptive-forms.md) l’ [exemple de formulaire](#sample-adaptive-form) de demande de prêt en formulaire adaptatif avec liaison de données. Veillez à ne pas cocher la **[!UICONTROL Generate adaptive form(s) without data bindings]** case lors de la génération du formulaire adaptatif.

![Formulaire adaptatif avec liaison JSON](assets/generate_af_with_data_bindings.png)

### Utiliser le schéma JSON comme source de données {#jsonwithdatabinding}

**** Cas d’utilisation : Vous générez un formulaire adaptatif avec liaison de données JSON à l’aide du service de conversion automatisée des formulaires. Le service de préremplissage et la fonction d’envoi de formulaire fonctionnent de manière transparente. Vous n’avez pas besoin d’étapes de configuration.

Avant d’exécuter le cas d’utilisation, assurez-vous que vous disposez [d’un formulaire adaptatif avec liaison](#generate-adaptive-forms-with-json-binding)de données.

Exécutez les étapes suivantes :

1. Sélectionnez à nouveau l’ **exemple de formulaire** de demande de prêt converti disponible dans le **[!UICONTROL output]** dossier et sélectionnez **[!UICONTROL Preview]** > **[!UICONTROL Preview with Data]**.</br>

   Télécharger le fichier de données d’exemple</br>

   [Obtenir le fichier](assets/loan_application_data_source_json_data_binding.txt)</br>

1. Si nécessaire, modifiez les valeurs de champ et envoyez le formulaire adaptatif. Les données envoyées sont disponibles à l’emplacement suivant dans le référentiel crx :

   `http://host name:port/crx/de/index.jsp#/content/forms/fp/admin/submit/data/latest file available in the folder`

## Convertir les données JSON du formulaire adaptatif envoyé au format XML {#convert-submitted-adaptive-form-data-to-xml}

Lorsque vous saisissez des valeurs dans des champs de formulaire adaptatif et que vous les envoyez, les données sont disponibles au format JSON dans le référentiel crx. Vous pouvez convertir le format des données JSON en XML à l’aide de l’API [org.apache.sling.commons.json.xml](https://sling.apache.org/apidocs/sling5/org/apache/sling/commons/json/xml/XML.html#toString) ou de l’exemple de code suivant :

```
import org.apache.sling.commons.json.JSONException;
import org.apache.sling.commons.json.JSONObject;
import org.apache.sling.commons.json.xml.XML;
 
public class ConversionUtils {
 
    public static String jsonToXML(String jsonString) throws JSONException {
        //https://sling.apache.org/apidocs/sling5/org/apache/sling/commons/json/xml/XML.html#toString(java.lang.Object)
        //jar - http://maven.ibiblio.org/maven2/org/apache/sling/org.apache.sling.commons.json/2.0.18/
        //Note: Need to extract boundData part before converting to XML
        return XML.toString(new JSONObject(jsonString));
    }
}
```
