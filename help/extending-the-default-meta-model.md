---
title: Étendre le méta-modèle par défaut
seo-title: Étendre le méta-modèle par défaut
description: Etendez le méta-modèle par défaut pour ajouter des modèles, des validations et des entités spécifiques à votre organisation et appliquer des configurations aux champs de formulaire adaptatif lors de l’exécution du service de conversion automatisée des formulaires.
seo-description: Etendez le méta-modèle par défaut pour ajouter des modèles, des validations et des entités spécifiques à votre organisation et appliquer des configurations aux champs de formulaire adaptatif lors de l’exécution du service de conversion automatisée des formulaires.
uuid: f98b4cca-f0a3-4db8-aef2-39b8ae462628
topic-tags: forms
discoiquuid: cad72699-4a4b-4c52-88a5-217298490a7c
translation-type: tm+mt
source-git-commit: 5d4dba8fea7439b991a7a15872e6f4ed48156ac9

---


# Étendre le méta-modèle par défaut {#extend-the-default-meta-model}

Le service de conversion automatisée des formulaires identifie et extrait les objets de formulaire des formulaires source. Le mappeur sémantique permet au service de déterminer comment les objets extraits sont représentés dans un formulaire adaptatif. Par exemple, un formulaire source peut avoir plusieurs types de représentations d’une date. Le mappeur sémantique permet de mapper toutes les représentations des objets de formulaire de date du formulaire source avec le composant de date des formulaires adaptatifs. Le mappeur sémantique permet également au service de préconfigurer et d’appliquer des validations, des règles, des modèles de données, du texte d’aide et des propriétés d’accessibilité aux composants de formulaire adaptatif pendant la conversion.

![](assets/meta-model.gif)

Meta-model est un schéma JSON. Avant de commencer avec le méta-modèle, assurez-vous que vous êtes bien familiarisé avec JSON. Vous devez posséder une expérience de création, de modification et de lecture de données enregistrées au format JSON.

## Méta-modèle par défaut {#default-meta-model}

Le service de conversion automatisée des formulaires comporte un méta-modèle par défaut. Il s’agit d’un schéma JSON et réside sur Adobe Cloud avec d’autres composants du service de conversion automatisée des formulaires. Vous trouverez une copie du méta-modèle sur votre serveur AEM local à l’adresse suivante :

http://&lt;serveur>:&lt;port>/aem/forms.html/content/dam/formsanddocuments/metamodel/global.schema.json.

Le schéma du méta-modèle est dérivé des entités de schéma à l’adresse https://schema.org/docs/schemas.html. Il comporte des entités telles que Person, PostalAddress, LocalBusiness et d’autres telles que définies sur https://schema.org. Chaque entité du méta-modèle adhère au type d’objet de schéma JSON. Le code suivant représente un exemple de structure de méta-modèle :

```
   "Entity": {
      "id": "Entity",
      "properties": {
        "name": {
          "type": "string"
        },

        "description": {
          "type": "string",
          "description": "Description of the item"
        }
      }
    }
```

## Téléchargement du méta-modèle par défaut {#download-the-default-meta-model}

Pour télécharger le méta-modèle par défaut sur le système de fichiers local, procédez comme suit :

1. Connectez-vous à votre instance AEM Forms.
1. Accédez au dossier **[!UICONTROL Forms]** > **[!UICONTROL Forms & Documents]** > **>** **[!UICONTROL Meta Model]** .
1. Sélectionnez le **[!UICONTROL global.schema.json]** fichier et appuyez sur **[!UICONTROL Download]**. Une boîte de dialogue de téléchargement s’affiche. Sélectionnez l’ **[!UICONTROL Download asset(s) as binary files]** option. Appuyer **[!UICONTROL Download]**. Une archive est téléchargée.

   <!--
   Comment Type: draft

   <li><p>Extract the archive and open the global.schema.json file for editing. </p> </li>
   -->

   <!--
   Comment Type: draft

   <li>Step text</li>
   -->

## Présentation du méta-modèle {#understanding-the-meta-model}

Un méta-modèle fait référence à un fichier de schéma JSON contenant des entités. Toutes les entités du fichier de schéma JSON comprennent un nom et un ID. Chaque entité peut inclure plusieurs propriétés. Les entités et ses propriétés peuvent varier en fonction du domaine. Vous pouvez développer un fichier de schéma avec des mots-clés et des configurations de champ pour mapper les propriétés de schéma aux composants de formulaire adaptatif.

```
"Event": {
      "id": "Eventid",
      "allOf": [
        {
          "$ref": "#Entity"
        },
        {
          "properties": {
            "startDate": {
              "type": "string",
              "format": "date",
              "description": "Specify the start date and time of the event in ISO 8601 date format."
            },
            "endDate": {
              "type": "string",
              "format": "date",
              "description": "Specify the end date and time of the event in ISO 8601 date format."
            },
            "location": {
              "$ref": "#PostalAddress",
              "description": "Specify the location of the event."
            }
          }
        }
      ]
    }
```

Dans cet exemple, **Event** représente le nom d’une entité avec une valeur **id** comme **Eventid**. L&#39;entité Evénement comprend plusieurs propriétés :

* startDate
* endDate
* location

Le concept **allOf** du méta-modèle permet l’héritage entre les entités.

Chaque propriété peut en outre inclure :

* [Propriétés du schéma JSON](#jsonschemaproperties)
* [Recherche par mot-clé pour appliquer des propriétés aux champs de formulaire adaptatif générés](#keywordsearch)
* [Propriétés supplémentaires](#additionalproperties)

![Propriétés de méta-modèle](assets/meta_model_elements.gif)

En fonction des mots-clés référencés à l’aide d’ **aem:affKeyword**, le service de conversion effectue une opération de recherche sur les champs du formulaire source. Le service de conversion applique les propriétés de schéma JSON et les propriétés supplémentaires aux champs qui répondent aux critères de recherche.

Dans cet exemple, le service de conversion recherche les mots-clés de téléphone, de téléphone, de téléphone mobile, de téléphone, de téléphone, de téléphone domestique, de numéro de téléphone, de numéro de téléphone et de numéro de téléphone dans le formulaire source. En fonction des champs qui incluent ces mots-clés, le service de conversion applique le type, le modèle et aem:afProperties aux champs du formulaire adaptatif après la conversion.

### Propriétés de schéma JSON pour les champs de formulaire adaptatif générés {#jsonschemaproperties}

Le méta-modèle prend en charge les propriétés communes de schéma JSON suivantes pour les champs de formulaire adaptatif générés à l’aide du service de conversion automatisée des formulaires :

<table> 
 <tbody> 
  <tr> 
   <th><strong>Nom de la propriété</strong></th> 
   <th><strong>Description</strong></th> 
  </tr> 
  <tr> 
   <td><p>titre</p></td> 
   <td> 
    <p>Le texte mentionné dans la propriété title d’un méta-modèle sert de mot-clé de recherche pour effectuer des actions sur les champs de formulaire adaptatif générés. Par exemple, la modification du libellé d’un champ de formulaire adaptatif. Pour plus d’informations, voir <strong>Modification du libellé d’un champ</strong> de formulaire dans les exemples de méta-modèles <a href="#custommetamodelexamples">personnalisés.</a></p> </td> 
  </tr>
  <td><p>description</p></td> 
   <td> 
    <p>La propriété description définit le texte d’aide pour le champ de formulaire adaptatif généré. Pour plus d’informations, voir <strong>Ajouter du texte d’aide à un champ</strong> de formulaire dans les exemples de méta-modèles <a href="#custommetamodelexamples">personnalisés.</a></p> </td> 
  </tr>
  <td><p>Type</p></td> 
   <td> 
    <p>La propriété type définit le type de données pour le champ de formulaire adaptatif généré. Les valeurs possibles de la propriété de titre sont les suivantes :</p>
    <ul> 
     <li>string : Génère un champ de formulaire adaptatif de type de données texte.</li> 
     <li>number : Génère un champ de formulaire adaptatif de type de données numériques.</li>
     <li>integer : Génère un champ de formulaire adaptatif de type de données numériques avec un sous-type défini sur integer.</li>
     <li>booléen : Génère un composant de formulaire adaptatif switch.</li>
     </ul><p>Pour plus d’informations sur l’utilisation de la propriété type dans un méta-modèle, voir <strong>Modification du type d’un champ</strong> de formulaire dans les exemples de méta-modèle <a href="#custommetamodelexamples">personnalisé.</a></p></td> 
  </tr>
  <td><p>pattern</p></td> 
   <td> 
    <p>La propriété pattern limite la valeur du champ de formulaire adaptatif généré en fonction d’une expression régulière. Par exemple, le code suivant du méta-modèle limite la valeur du champ de formulaire adaptatif généré à dix chiffres:<br>"modèle" : "/\\d{10}/"<br>De même, le code suivant du méta-modèle limite la valeur d’un champ à un format de date spécifique.<br> "pattern" : "date{JJ MMMM, AAAA}",</p> </td> 
  </tr>
  <td><p>format</p></td> 
   <td> 
    <p>La propriété format limite la valeur du champ de formulaire adaptatif généré en fonction d’un modèle nommé au lieu d’une expression régulière. Les valeurs possibles de la propriété format sont les suivantes :<ul><li>email : Génère un composant de formulaire adaptatif de courrier électronique.</li><li>hostname : Génère un composant de formulaire adaptatif textbox.</li></ul>Pour plus d’informations sur l’utilisation de la propriété format dans un méta-modèle, voir <strong>Modification du format d’un champ</strong> de formulaire dans des exemples de méta-modèle <a href="#custommetamodelexamples">personnalisés.</a></p> </td> 
  </tr>
  <td><p>enum et enumNames</p></td> 
   <td> 
    <p>Les propriétés enum et enumNames limitent les valeurs des champs de liste déroulante, de case à cocher ou de bouton radio à un jeu fixe. Les valeurs répertoriées dans enumNames sont affichées dans l’interface utilisateur. Les valeurs répertoriées à l’aide de la propriété enum sont utilisées pour le calcul.<br>Pour plus d’informations, voir <strong>Conversion d’un champ de formulaire en cases à cocher à choix multiples dans le formulaire</strong>adaptatif, <strong>Conversion d’un champ de texte en liste déroulante dans le formulaire</strong>adaptatif et <strong>Ajout d’options supplémentaires à la liste</strong> déroulante dans les exemples de méta-modèles <a href="#custommetamodelexamples">personnalisés.</a></p> </td> 
  </tr>
 </tbody> 
</table>

### Recherche par mot-clé pour appliquer des propriétés aux champs de formulaire adaptatif générés {#keywordsearch}

Le service de conversion automatisée des formulaires effectue une recherche par mot-clé sur le formulaire source pendant la conversion. Après avoir filtré les champs qui répondent aux critères de recherche, le service de conversion applique les propriétés définies pour ces champs dans le méta-modèle aux champs de formulaire adaptatif générés.

Les mots-clés sont référencés à l’aide de la propriété **aem:affKeyword** .

```
{
  "numberfields": {
      "type": "number",
      "aem:affKeyword": ["Bank account number"]
 }
}
```

Dans cet exemple, le service de conversion utilise le texte dans **aem:affKeyword** comme mot-clé de recherche. Après avoir récupéré le texte du numéro **de compte** bancaire dans le formulaire, le service de conversion convertit le champ en type de **nombre** à l’aide de la propriété **type** .

### Propriétés supplémentaires pour les champs de formulaire adaptatif générés {#additionalproperties}

Vous pouvez utiliser la propriété **aem:afProperties** dans le méta-modèle pour définir les propriétés supplémentaires suivantes pour les champs de formulaires adaptatifs générés à l’aide du service de conversion automatisée des formulaires :

<table> 
 <tbody> 
  <tr> 
   <th><strong>Nom de la propriété</strong></th> 
   <th><strong>Description</strong></th> 
  </tr> 
  <tr> 
   <td><p>multiLine</p></td> 
   <td> 
    <p>La propriété multiligne convertit un champ de formulaire source en champ multiligne dans le formulaire adaptatif après la conversion. Pour plus d’informations, voir <strong>Conversion d’un champ de chaîne en champ</strong> multiligne dans les exemples de méta-modèle <a href="#custommetamodelexamples">personnalisé.</a></p> </td> 
  </tr>
  <td><p>mandatory</p></td> 
   <td> 
    <p>La propriété mandatory définit comme obligatoire l’entrée d’un champ de formulaire adaptatif après la conversion.<br>Pour plus d’informations, voir <strong>Ajout de validations aux champs</strong> de formulaire adaptatif dans les exemples de méta-modèles <a href="#custommetamodelexamples">personnalisés.</a></p>
    </td> 
  </tr>
  <td><p>jcr:title</p></td> 
   <td> 
    <p>La propriété jcr:title, avec la propriété de schéma JSON de titre, vous permet de modifier le libellé d’un champ de formulaire adaptatif après la conversion.<br>Pour plus d’informations, voir <strong>Modification du libellé d’un champ</strong> de formulaire dans les exemples de méta-modèles <a href="#custommetamodelexamples">personnalisés.</a><br>Voir <a href="https://helpx.adobe.com/experience-manager/6-5/forms/using/adaptive-form-json-schema-form-model.html" target="_blank">Création de formulaires adaptatifs à l’aide d’un schéma</a> JSON pour en savoir plus sur les propriétés que vous pouvez appliquer aux champs de formulaire adaptatif à l’aide d’un schéma JSON.</p>
    <p></p></td> 
  </tr>
  <td><p>sling:resourceType et guideNodeClass</p></td> 
   <td> 
    <p>Les propriétés sling:resourceType et guideNodeClass vous permettent de mapper un champ de formulaire à un composant de formulaire adaptatif correspondant.<br>Pour plus d’informations, voir <strong>Conversion d’un champ de formulaire en cases à cocher à choix multiples dans le formulaire</strong> adaptatif et <strong>Conversion d’un champ de texte en liste déroulante dans le formulaire</strong> adaptatif dans les exemples de méta-modèle <a href="#custommetamodelexamples">personnalisé.</a></p> </td> 
  </tr>
  <td><p>validatePictureClause</p></td> 
   <td> 
    <p>La propriété validatePictureClause définit une validation sur le format autorisé dans le champ de formulaire adaptatif après la conversion.<br>Pour plus d’informations, voir <strong>Ajout de validations aux champs</strong> de formulaire adaptatif dans les exemples de méta-modèles <a href="#custommetamodelexamples">personnalisés.</p> </td> 
  </tr>
 </tbody> 
</table>

## Modification des champs d’un formulaire adaptatif à l’aide d’un méta-modèle personnalisé {#modify-adaptive-form-fields-using-custom-meta-model}

Votre entreprise peut avoir des modèles et des validations en plus de ceux répertoriés dans le méta-modèle par défaut. Vous pouvez étendre le méta-modèle par défaut pour ajouter des modèles, des validations et des entités spécifiques à votre organisation. Le service de conversion automatisée des formulaires applique le méta-modèle personnalisé aux champs du formulaire pendant la conversion. Vous pouvez continuer à mettre à jour le méta-modèle au fur et à mesure que de nouveaux modèles, validations et entités propres à votre organisation sont découverts.

Le service de conversion automatisée des formulaires utilise un méta-modèle par défaut enregistré à l’emplacement suivant pour mapper les champs de formulaire source aux champs de formulaire adaptatif pendant la conversion :

http://&lt;serveur>:&lt;port>/aem/forms.html/content/dam/formsanddocuments/metamodel/global.schema.json

Cependant, vous pouvez enregistrer un méta-modèle personnalisé dans un dossier et modifier les propriétés du service de conversion pour utiliser le méta-modèle personnalisé pendant la conversion.

### Utiliser un méta-modèle personnalisé pendant la conversion {#use-custom-meta-model-during-conversion}

Exécutez les étapes suivantes pour utiliser un méta-modèle personnalisé pendant la conversion :

1. Créez un dossier dans **[!UICONTROL Forms]** > **[!UICONTROL Forms & Documents]** et téléchargez le fichier de schéma JSON de méta-modèle personnalisé dans le dossier.
1. Ouvrez les propriétés du service de conversion à l’aide de :

   **[!UICONTROL Tools]** > **[!UICONTROL Cloud Services]** > **[!UICONTROL Automated Forms Conversion Configuration]**> **&lt;** Propriétés de la configuration **sélectionnée>**

1. Dans l’ **[!UICONTROL Basic]** onglet, spécifiez l’emplacement du méta-modèle personnalisé dans le **[!UICONTROL Custom Meta-model]** champ et appuyez sur **[!UICONTROL Save & Close]**.
1. [Exécutez la conversion](convert-existing-forms-to-adaptive-forms.md#start-the-conversion-process) pour appliquer le méta-modèle personnalisé au processus de conversion.

### Exemples de méta-modèles personnalisés {#custommetamodelexamples}

Voici quelques exemples courants d’utilisation d’un méta-modèle personnalisé pour modifier les propriétés de champ de formulaire adaptatif :

* Modification du libellé d’un champ de formulaire
* Modification du type d’un champ de formulaire
* Ajout de texte d’aide à un champ de formulaire
* Convertir un champ de formulaire en boutons radio à choix multiples dans le formulaire adaptatif
* Modification du format d’un champ de formulaire
* Ajout de validations aux champs de formulaire adaptatif
* Convertir un champ de formulaire en options de liste déroulante dans le formulaire adaptatif
* Ajouter des options supplémentaires à la liste déroulante
* Convertir un champ de chaîne en champ multiligne

#### Modification du libellé d’un champ de formulaire {#modify-the-label-of-a-form-field}

**** Exemple : Modifiez le libellé du numéro de compte bancaire dans le formulaire en Numéro de compte personnalisé dans le formulaire adaptatif après la conversion.

Dans ce méta-modèle personnalisé, le service de conversion utilise la propriété **title** comme mot-clé de recherche. Après avoir récupéré le texte du numéro **de compte** bancaire dans le formulaire, le service de conversion remplace le texte par la chaîne du numéro **de compte** du client mentionnée avec la propriété **jcr:title** de la section **aem:afProperties.**

```
{
  "numberfields": {
      "type": "number",
   "title": "Bank account number",
   "aem:afProperties" : {
    "jcr:title" : "Customer account number"
   }
   }
}
```

#### Modification du type d’un champ de formulaire {#modify-the-type-of-a-form-field}

**Exemple**: Modifiez le champ du numéro **** de compte bancaire du type de texte dans le formulaire avant de le convertir en champ de type numérique dans le formulaire adaptatif après la conversion.

Dans ce méta-modèle personnalisé, le service de conversion utilise le texte dans **aem:affKeyword** comme mot-clé de recherche. Après avoir récupéré le texte du numéro **de compte** bancaire dans le formulaire, le service de conversion convertit le champ en un type de nombre à l’aide de la propriété **type** .

```
{
  "numberfields": {
      "type": "number",
      "aem:affKeyword": ["Bank account number"]
 }
}
```

#### Ajout de texte d’aide à un champ de formulaire {#add-help-text-to-a-form-field}

**Exemple**: Ajoutez du texte d’aide au champ Numéro **** de compte bancaire du formulaire adaptatif.

Dans ce méta-modèle personnalisé, le service de conversion utilise le texte dans **aem:affKeyword** comme mot-clé de recherche. Après avoir récupéré le texte du numéro **de compte** bancaire dans le formulaire, le service de conversion ajoute le texte Aide au champ du formulaire adaptatif à l’aide de la propriété **description** .

```
{
  "numberfields": {
      "type": "number",
      "aem:affKeyword": ["Bank account number"],
   "description": "Specify your bank account number."
 }
}
```

#### Conversion d’un champ de formulaire en cases à cocher à choix multiples dans le formulaire adaptatif {#convert-a-form-field-to-multiple-choice-check-boxes-in-the-adaptive-form}

**Exemple**: Convertissez le champ **Pays** du type chaîne dans le formulaire avant conversion en cases à cocher dans le formulaire adaptatif après conversion.

Dans ce méta-modèle personnalisé, le service de conversion utilise le texte dans **aem:affKeyword** comme mot-clé de recherche. Après avoir récupéré le texte **Pays** dans le formulaire, le service de conversion convertit le champ en cases à cocher à l’aide de la propriété **enum** :

* Inde
* Angleterre
* Australie
* Nouvelle-Zélande

**les propriétés sling:resourceType** et **guideNodeClass** mappent un champ de formulaire au composant de formulaire adaptatif de la case à cocher.

```
{
"title": {
    "aem:affKeyword": [
      "country"
    ],
    "type" : "string",
    "enum": [
      "India",
      "England",
      "Australia",
      "New Zealand"
    ],
    "aem:afProperties": {
      "sling:resourceType": "fd/af/components/guidecheckbox",
      "guideNodeClass": "guidecheckbox"
    }
  }
}
```

#### Modification du format d’un champ de formulaire {#modify-the-format-of-a-form-field}

**Exemple**: Modifiez le format du champ Adresse **de** courriel en format de courriel.

Dans ce méta-modèle personnalisé, le service de conversion utilise le texte dans **aem:affKeyword** comme mot-clé de recherche. Après avoir récupéré le texte d’adresse **de** courriel dans le formulaire, le service de conversion convertit le champ dans un format de courrier électronique à l’aide de la propriété **format** .

```
{
   "additionalDetails" : {
      "aem:affKeyword": ["E-mail Address"],
       "type" : "string",
       "format" : "email"
  } 
}
```

#### Ajout de validations aux champs de formulaire adaptatif {#add-validations-to-adaptive-form-fields}

**** Exemple 1 : Ajoutez une validation au champ Code **** postal du formulaire adaptatif.

Dans ce méta-modèle personnalisé, le service de conversion utilise le texte dans **aem:affKeyword** comme mot-clé de recherche. Après avoir récupéré le texte Code **** postal dans le formulaire, le service de conversion ajoute une validation au champ à l’aide de la propriété **validatePictureClause** définie dans la section **aem:afProperties** . En fonction de la validation, l’entrée que vous spécifiez pour le champ Code **** postal dans le formulaire adaptatif après la conversion doit comporter six caractères.

```
{
   "postalCode" : {
      "aem:affKeyword": ["Postal Code"],
      "type" : "string",
      "aem:afProperties" : {
        "validatePictureClause" : "\\d{6}"
      } 
   }
}
```

**** Exemple 2 : Ajoutez une validation au champ du numéro **de compte** bancaire du formulaire adaptatif.

Dans ce méta-modèle personnalisé, le service de conversion utilise le texte dans **aem:affKeyword** comme mot-clé de recherche. Après avoir récupéré le texte du numéro **de compte** bancaire dans le formulaire, le service de conversion ajoute une validation au champ à l’aide de la propriété **obligatoire** définie dans la section **aem:afProperties** . En fonction de la validation, vous devez spécifier une valeur pour le champ du numéro **de compte** bancaire avant d’envoyer le formulaire après la conversion.

```
{
  "numberfields": {
      "type": "number",
      "aem:affKeyword": ["Bank account number"],
   "aem:afProperties" : {
        "mandatory": "true"
      }   
   }
}
```

#### Convertir un champ de texte en liste déroulante dans le formulaire adaptatif {#convert-a-text-field-to-drop-down-list-in-the-adaptive-form}

**Exemple**: Convertissez le champ **Pays** du type chaîne dans le formulaire avant conversion en options déroulantes dans le formulaire adaptatif après conversion.

Dans ce méta-modèle personnalisé, le service de conversion utilise le texte dans **aem:affKeyword** comme mot-clé de recherche. Après avoir récupéré le texte **Pays** dans le formulaire, le service de conversion convertit le champ en options de liste déroulante suivantes à l’aide de la propriété **enum** :

* Inde
* Angleterre
* Australie
* Nouvelle-Zélande

**les propriétés sling:resourceType** et **guideNodeClass** mappent un champ de formulaire au composant de formulaire adaptatif déroulant.

```
{
"title": {
    "aem:affKeyword": [
      "country"
    ],
    "type" : "string",
    "enum": [
      "India",
      "England",
      "Australia",
      "New Zealand"
    ],
    "aem:afProperties": {
      "sling:resourceType": "fd/af/components/guidedropdownlist",
      "guideNodeClass": "guideDropDownlist"
    }
  }
}
```

#### Ajouter des options supplémentaires à la liste déroulante {#add-additional-options-to-the-drop-down-list}

**** Exemple : Ajoutez **Sri Lanka** comme option supplémentaire à une liste déroulante existante à l’aide d’un méta-modèle personnalisé.

Pour ajouter une option supplémentaire, mettez à jour la propriété **enum** avec la nouvelle option. Dans cet exemple, mettez à jour la propriété **enum** avec **Sri Lanka** comme option supplémentaire. Les valeurs répertoriées dans la propriété **enum** s’affichent dans la liste déroulante.

```
{
"title": {
    "aem:affKeyword": [
      "country"
    ],
    "type" : "string",
    "enum": [
      "India",
      "England",
      "Australia",
      "New Zealand",
   "Sri Lanka"
    ],
    "aem:afProperties": {
      "sling:resourceType": "fd/af/components/guidecheckbox",
      "guideNodeClass": "guidecheckbox"
    }
  }
}
```

#### Convertir un champ de chaîne en champ multiligne {#convert-a-string-field-to-a-multi-line-field}

**** Exemple : Convertissez le champ **Adresse** de type chaîne en champ multiligne dans le formulaire après la conversion.

Dans ce méta-modèle personnalisé, le service de conversion utilise le texte dans **aem:affKeyword** comme mot-clé de recherche. Après avoir récupéré le texte **Adresse** dans le formulaire, le service convertit le champ de texte en champ multiligne à l’aide de la propriété **multiligne** définie dans la section **aem:afProperties** .

```
{
 "multiline" : {
   "aem:affKeyword": [
      "Address"
    ],
    "type" : "string",
    "aem:afProperties": {
      "multiline": "true"
    }
  }
}
```
