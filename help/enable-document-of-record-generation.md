---
title: Générer un document d’enregistrement pendant la conversion
seo-title: Générer un document d’enregistrement pendant la conversion
description: Chemins recommandés pour générer un DE en fonction du type de formulaire source utilisé pour la conversion.
seo-description: Chemins recommandés pour générer un DE en fonction du type de formulaire source utilisé pour la conversion.
page-status-flag: never-activated
uuid: 7f0f5bf3-21be-449a-b23e-5946a9fd7ed4
contentOwner: khsingh
discoiquuid: 75f6e6bc-7636-4b40-919c-8b20a6ccbb1f
translation-type: tm+mt
source-git-commit: 640d72d7961ef0c2393bf0ae6745d918e388a056

---


# Processus recommandés pour activer la génération de documents d’enregistrement pour les formulaires adaptatifs {#recommended-workflows-dor-generation}

Le document d’enregistrement (DE) vous permet de conserver un enregistrement des informations que vous fournissez et envoyez dans un formulaire adaptatif afin que vous puissiez y faire référence ultérieurement.
Le DE utilise un modèle de base pour définir sa disposition. Vous pouvez générer un DE à l’aide d’un modèle par défaut ou en associant un autre modèle au formulaire adaptatif.

![Document d’enregistrement généré](assets/document_of_record.gif)

Pour plus d’informations sur la génération d’un DE, voir [Générer un document d’enregistrement pour les formulaires](https://helpx.adobe.com/experience-manager/6-5/forms/using/generate-document-of-record-for-non-xfa-based-adaptive-forms.html)adaptatifs.

Le service [Conversion](../help/introduction.md) automatisée des formulaires convertit les formulaires source suivants en formulaires adaptatifs :

* formulaires PDF non interactifs
* Formulaires Acro
* Formulaires PDF XFA

Selon le formulaire source que vous utilisez pour la conversion, vous pouvez générer un DE à l’aide de :

* un modèle par défaut
* le formulaire source comme modèle : si vous sélectionnez cette option, le service de conversion associe automatiquement le formulaire source au formulaire adaptatif converti comme modèle de DE.
* associer tout autre modèle au formulaire adaptatif converti

Le tableau suivant illustre un exemple de l’impact du modèle de DE que vous utilisez sur la disposition du DE généré :

<table> 
 <tbody>
 <tr>
  <td><p><strong>Formulaire source</strong></p></td>
  <td><p><strong>DE généré</strong></p></td> 
   </tr>
  <tr>
   <td><img src="assets/source_xdp_updated.png"/></td>
   <td><p>Si vous utilisez le modèle par défaut pour générer un DE :</br><img src="assets/source_form_default_updated.png"/></td>
   </tr>
   <tr>
   <td></td>
   <td><p>Si vous utilisez le formulaire source comme modèle pour générer le DE :</br></p><img src="assets/source_form_dor_updated.png"/></td>
   </tr>
  </tbody>
</table>

Comme illustré dans le tableau, si vous utilisez le formulaire source comme modèle, le DE conserve la disposition du formulaire source.
Cet article décrit les chemins recommandés pour générer un DE en fonction des trois types de formulaires source.

<table> 
 <tbody> 
  <tr> 
   <th><strong>Formulaire source</strong></th> 
   <th><strong>Méthodes de génération de DE</strong></th> 
  </tr> 
  <tr> 
   <td><p>Formulaires PDF non interactifs</p></td> 
   <td> 
    <ul> 
     <li><a href="#generate-document-of-record-using-cloud-configuration">Activer la génération de DE avant la conversion de formulaire adaptatif pour générer un DE à l’aide d’un modèle par défaut</a></li> 
     <li><a href="#edit-adaptive-form-properties-generate-document-of-record">Modifier les propriétés de formulaire adaptatif après la conversion de formulaire adaptatif pour activer la génération de DE à l’aide de la valeur par défaut ou de tout autre modèle de formulaire</a></li> 
    </ul> </td> 
  </tr>
  <tr> 
   <td><p>Formulaires Acro ou formulaires PDF XFA</p></td> 
   <td> 
    <ul> 
     <li><a href="#use-input-form-as-template-to-generate-document-of-record">Activer la génération de DE avant la conversion de formulaire adaptatif pour générer un DE à l’aide du formulaire source comme modèle</a></li> 
     <li><a href="#edit-adaptive-form-properties-to-generate-document-of-record">Modifiez les propriétés du formulaire adaptatif après la conversion du formulaire adaptatif pour activer la génération de DE à l’aide du modèle par défaut, du formulaire source comme modèle ou de tout autre modèle de formulaire.</a></li> 
    </ul> </td> 
  </tr>    
 </tbody> 
</table>

## Générer un document d’enregistrement pour les formulaires PDF non interactifs {#generate-document-of-record-non-interactive-pdf}

Si vous utilisez un formulaire PDF non interactif comme formulaire source pour le service de conversion automatisée des formulaires, vous pouvez :

* activer la génération de DE avant la conversion de formulaire adaptatif pour générer un DE à l’aide d’un modèle par défaut ;
* ou modifier les propriétés du formulaire adaptatif après la conversion du formulaire adaptatif pour activer la génération de DE à l’aide de la valeur par défaut ou de tout autre modèle de formulaire

### Activer la génération de DE avant la conversion pour générer des DE à l’aide du modèle par défaut {#generate-document-of-record-using-cloud-configuration}

1. Sélectionnez **[!UICONTROL Tools]** > **[!UICONTROL Cloud Services]** > **[!UICONTROL Automated Forms Conversion Configuration]** > Propriétés de la configuration du cloud utilisée pour la conversion > **[!UICONTROL Advanced]** > option **[!UICONTROL Generate Document of Record]** .

   ![Générer un document d’enregistrement à l’aide de la configuration Cloud](assets/generate_dor_cloud_config.gif)

1. Tap **[!UICONTROL Save & Close]** to save the settings.

1. [Exécutez la conversion](../help/convert-existing-forms-to-adaptive-forms.md). Veillez à utiliser la configuration de cloud modifiée à l’étape 1 de ces instructions.
Lors de l’envoi du formulaire adaptatif converti, le DE est généré automatiquement à l’aide du modèle par défaut.

### Modifier les propriétés de formulaire adaptatif après la conversion pour activer la génération de DE {#edit-adaptive-form-properties-generate-document-of-record}

Si vous n’activez pas la génération de DE avant de convertir le formulaire source en formulaire adaptatif, vous pouvez continuer à le faire après la conversion.

1. [Exécutez la conversion](../help/convert-existing-forms-to-adaptive-forms.md) sur le formulaire PDF non interactif pour générer un formulaire adaptatif.

1. Sélectionnez le formulaire adaptatif dans le **[!UICONTROL output]** dossier et appuyez sur **[!UICONTROL Properties]**.

1. Dans l’ **[!UICONTROL Form Model]** onglet, développez la **[!UICONTROL Document of Record Template Configuration]** section et sélectionnez **[!UICONTROL Generate Document of Record]**.

   ![Générer un document d’enregistrement](assets/generate_dor_af_properties.png)

1. Tap **[!UICONTROL Save & Close]** to save the settings.

Lors de l’envoi du formulaire adaptatif converti, le DE est généré automatiquement à l’aide du modèle par défaut. Si vous souhaitez associer un autre modèle de DE au formulaire adaptatif converti, vous pouvez sélectionner **[!UICONTROL Associate form template as the Document of Record template]** une option.

## Générer un document d’enregistrement pour les formulaires PDF Acro Forms ou XFA {#generate-document-of-record-acroform-xfaform}

Si vous utilisez un formulaire Acro ou un formulaire PDF XFA comme formulaire source pour le service de conversion automatisée des formulaires, vous pouvez :

* activer la génération de DE avant la conversion de formulaire adaptatif pour générer le DE à l’aide du formulaire source comme modèle

* ou modifier les propriétés du formulaire adaptatif après la conversion du formulaire adaptatif pour activer la génération de DE à l’aide du modèle par défaut, du formulaire source comme modèle ou de tout autre modèle de formulaire

### Activer la génération de DE avant la conversion pour générer de DE à l’aide du modèle de formulaire source {#use-input-form-as-template-to-generate-document-of-record}

1. Sélectionnez **[!UICONTROL Tools]** > **[!UICONTROL Cloud Services]** > **[!UICONTROL Automated Forms Conversion Configuration]** > Propriétés de la configuration du cloud utilisée pour la conversion > **[!UICONTROL Advanced]** > option **[!UICONTROL Generate Document of Record]** .

1. Tap **[!UICONTROL Save & Close]** to save the settings.

1. [Exécutez la conversion](../help/convert-existing-forms-to-adaptive-forms.md). Veillez à utiliser la configuration de cloud modifiée à l’étape 1 de ces instructions.
Le service de conversion associe automatiquement le formulaire Acro ou le formulaire PDF XFA au formulaire adaptatif converti comme modèle de DE.
Vous pouvez ouvrir les propriétés du formulaire adaptatif pour afficher le modèle de DE dans la **[!UICONTROL Document of Record Template Configuration]** section de **[!UICONTROL Form Model]** l’onglet.

   ![Modifier les propriétés du formulaire adaptatif pour générer un document d’enregistrement](assets/generate_dor_af_properties_xdp_acro.png)

   Lors de l’envoi du formulaire adaptatif converti, le DE est généré automatiquement à l’aide du modèle de formulaire source.

### Modifier les propriétés de formulaire adaptatif après la conversion pour activer la génération de DE {#edit-adaptive-form-properties-to-generate-document-of-record}

1. [Exécutez la conversion](../help/convert-existing-forms-to-adaptive-forms.md) sur le formulaire PDF non interactif pour générer un formulaire adaptatif.

1. Sélectionnez le formulaire adaptatif dans le **[!UICONTROL output]** dossier et appuyez sur **[!UICONTROL Properties]**.

1. Dans l’ **[!UICONTROL Form Model]** onglet, développez la **[!UICONTROL Document of Record Template Configuration]** section et sélectionnez **[!UICONTROL Generate Document of Record]** pour activer la génération de DE à l’aide du modèle par défaut.
Vous pouvez également sélectionner l’ **[!UICONTROL Associate form template as the Document of Record template]** option et sélectionner le modèle pour activer la génération de DE à l’aide du modèle de formulaire source ou de tout autre modèle de formulaire.

1. Tap **[!UICONTROL Save & Close]** to save the settings.
