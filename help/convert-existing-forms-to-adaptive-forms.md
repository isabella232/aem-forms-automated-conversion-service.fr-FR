---
title: 'Conversion de formulaires PDF en formulaires adaptatifs '
seo-title: 'Conversion de formulaires PDF en formulaires adaptatifs '
description: Exécution du service de conversion de formulaires automatisés pour convertir des formulaires PDF en formulaires adaptatifs
seo-description: Exécution du service de conversion de formulaires automatisés pour convertir des formulaires PDF en formulaires adaptatifs
uuid: 49fcd5c0-0e72-496d-9831-00f79d582f57
contentOwner: khsingh
topic-tags: forms
discoiquuid: 9358219c-6079-4552-92b9-b427a23811af
translation-type: tm+mt
source-git-commit: c0ca850a0a1e82e34364766601011d6367b218ac

---


# Conversion de formulaires PDF en formulaires adaptatifs {#convert-print-forms-to-adaptive-forms}

Le service de conversion automatisée des formulaires AEM Forms, proposé par Adobe Sensei, convertit automatiquement vos formulaires PDF en formulaires adaptatifs adaptés aux périphériques et réactifs. Que vous utilisiez des formulaires PDF non interactifs, des formulaires Acro Forms ou des formulaires PDF XFA, le service de conversion automatisée de formulaires peut facilement convertir ces formulaires en formulaires adaptatifs. Pour plus d’informations sur les fonctionnalités, le processus de conversion et les informations d’intégration, voir Service de conversion [](introduction.md) automatisée des formulaires.

## Conditions préalables {#pre-requisites}

* [**Configuration du service de conversion **](configure-service.md)

* **Préparez les[modèles](https://helpx.adobe.com/experience-manager/6-5/forms/using/template-editor.html)à appliquer aux formulaires convertis :** L’utilisation d’un modèle vous permet d’appliquer une marque cohérente à tous les formulaires adaptatifs. De plus, le service de conversion automatisée des formulaires n’extrait pas et n’utilise pas l’en-tête et le pied de page des  PDF source. Vous pouvez utiliser des modèles de formulaire adaptatif pour spécifier l’en-tête et le pied de page. L’en-tête et le pied de page spécifiés dans le modèle sont appliqués au formulaire adaptatif pendant la conversion.

* **Préparez le[](https://helpx.adobe.com/experience-manager/6-5/forms/using/themes.html)à appliquer aux formulaires convertis :** L’utilisation d’un thème vous permet d’appliquer un style cohérent à tous les formulaires adaptatifs de votre organisation.

##  le processus de conversion {#start-the-conversion-process}

Après avoir connecté votre instance AEM au service de conversion d’AEM Forms, vous pouvez convertir vos formulaires PDF en formulaires adaptatifs. Effectuez les étapes suivantes dans l’ordre répertorié pour convertir les formulaires :

* [Téléchargement de formulaires PDF vers votre serveur AEM Forms](convert-existing-forms-to-adaptive-forms.md#upload-pdf-forms-to-your-aem-forms-server)
* [Exécution de la conversion](convert-existing-forms-to-adaptive-forms.md#run-the-conversion)
* [Vérification et correction des formulaires convertis](review-correct-ui-edited.md)

### Téléchargement de formulaires PDF vers votre serveur AEM Forms {#upload-pdf-forms-to-your-aem-forms-server}

Le service de conversion convertit les formulaires PDF disponibles sur votre instance AEM Forms en formulaires adaptatifs. Vous pouvez télécharger tous les formulaires PDF en une seule ou en plusieurs fois, selon les besoins. Avant de télécharger les formulaires, tenez compte des éléments suivants :

* N’enregistrez pas plus de 15 formulaires dans un dossier et veillez à ce que le nombre total de pages dans un dossier ne dépasse pas 50.
* Veillez à ce que la taille du dossier ne dépasse pas 10 Mo. Ne conservez pas les formulaires dans un sous-dossier.
* Veillez à ce qu’un formulaire ne dépasse pas 15 pages.
* Ne téléchargez pas de formulaires protégés. Le service ne convertit pas les formulaires protégés par mot de passe et sécurisés.
* Ne téléchargez pas de formulaires PDF sources dont le nom comporte des espaces. Supprimez l’espace du nom du fichier avant de télécharger les formulaires.
* Do not upload [PDF Portfolios](https://helpx.adobe.com/acrobat/using/overview-pdf-portfolios.html). Le service ne convertit pas un portfolio PDF en formulaire adaptatif.
* Lisez les sections Problèmes [connus et](known-issues.md) Meilleures pratiques et considérations [](styles-and-pattern-considerations-and-best-practices.md) et apportez les modifications suggérées aux formulaires.

Effectuez les étapes suivantes pour télécharger les formulaires à convertir dans un dossier de votre instance AEM Forms :

1. Connectez-vous à l’instance AEM Forms.

1. Tap **[!UICONTROL Adobe Experience Manager]** ![](assets/adobeexperiencemanager.png) > **[!UICONTROL Navigation]** ![](assets/compass.png) > **[!UICONTROL Forms]** > **[!UICONTROL Forms & Documents]**.
1. Appuyer **[!UICONTROL Create]**> **[!UICONTROL Folder]**. Indiquez **Titre** et **Nom** du dossier. Appuyer **[!UICONTROL Create]**. Un dossier est créé.
1. Appuyez sur pour ouvrir le dossier nouvellement créé.
1. Appuyer **[!UICONTROL Create]**> **[!UICONTROL File Upload]**. Sélectionnez les formulaires à télécharger, cliquez sur **[!UICONTROL Open]**, puis sur **[!UICONTROL Upload]**. Les formulaires sont téléchargés.

### Exécution de la conversion {#run-the-conversion}

Après avoir téléchargé les formulaires et configuré le service, procédez comme suit pour de la conversion :

1. Sur votre instance AEM Forms, appuyez sur **[!UICONTROL Adobe Experience Manager]** Boîte de dialogue ![Paramètres de](assets/adobeexperiencemanager.png) conversion > **[!UICONTROL Navigation]** > ![](assets/compass.png) > **[!UICONTROL Forms]** **[!UICONTROL Forms & Documents]**.
1. Sélectionnez un formulaire ou le dossier contenant des formulaires PDF (formulaires à convertir) et appuyez sur **[!UICONTROL Start Automated Conversion]**. The **[!UICONTROL Conversion Settings]** dialog appears.

   ![Définition des configurations](assets/conversion-settings-dialog.png)

1. Dans l’ **[!UICONTROL Basic]** onglet de la boîte de dialogue Paramètres de conversion :

   * **[!UICONTROL Select a cloud configuration]**. Lorsque vous sélectionnez une configuration, le modèle et le thème par défaut sont déjà spécifiés. Vous pouvez spécifier un modèle ou un thème différent, si nécessaire.
   * Spécifiez un emplacement pour enregistrer les formulaires adaptatifs générés et les  de correspondants. Vous pouvez utiliser des chemins par défaut ou spécifier des chemins personnalisés.
   * Utilisez l’option **Générer des formulaires adaptatifs sans liaison** de modèle de données pour sélectionner si vous souhaitez générer un formulaire adaptatif avec ou sans liaison de modèle de données.
Si vous ne sélectionnez pas cette option, le service de conversion associe automatiquement les formulaires adaptatifs à un  JSON et crée une liaison de données entre les champs disponibles dans le formulaire adaptatif et le JSON. Le **[!UICONTROL Save generated data model schema at]** champ affiche l’emplacement par défaut pour enregistrer le  JSON généré. Vous pouvez également personnaliser l’emplacement pour enregistrer le  de généré.
Si vous sélectionnez cette option, le service de conversion génère un formulaire adaptatif sans liaisons de modèle de données. Après une conversion réussie, vous pouvez associer un formulaire adaptatif à un modèle de données de formulaire, à un  XML ou à un  JSON. For more information, see [Creating an adaptive form](https://helpx.adobe.com/experience-manager/6-5/forms/using/creating-adaptive-form.html).
   <!--
   Comment Type: draft

   <note type="note">
   <p>The XDP or XFA-based PDF form is not used to generate the Document of Record. The conversion service auto-generates the Document of Record only if you enable the Tools &gt; Cloud Services &gt; Automated Forms Conversion Configuration &gt; <strong>&lt;Properties of selected configuration&gt; &gt;</strong> Advanced &gt; Generate Document of Record option.</p>
   <p> </p>
   </note>
   -->

1. Dans l’ **[!UICONTROL Additional]** onglet de la boîte de dialogue Paramètres de conversion,
   * Sélectionnez l’ **[!UICONTROL Extract fragment from adaptive forms]** option permettant au service de conversion d’identifier, d’extraire et de télécharger des fragments de formulaire pour les formulaires convertis. Lorsque vous sélectionnez l’ **[!UICONTROL Extract fragment from adaptive forms]** option, les options permettant de spécifier les chemins d’enregistrement des fragments de formulaire extraits et des fragments de formulaire correspondants  sont activées.
   * Spécifiez l’emplacement de **[!UICONTROL existing adaptive form fragments]**, si vous avez des  JSON existants basés sur et des  moins de fragments de formulaire adaptatif et si vous prévoyez d’utiliser ces fragments dans des formulaires adaptatifs générés automatiquement. Le service de conversion correspond aux  JSON disponibles basés sur et aux  moins de fragments de formulaire adaptatif avec des formulaires PDF d’entrée (formulaires PDF non interactifs uniquement). S’il existe une correspondance, le fragment de formulaire adaptatif correspondant est utilisé dans les formulaires adaptatifs correspondants.
   >[!NOTE]
   >
   >
   > * Vous pouvez utiliser uniquement **[!UICONTROL  Extract Fragment]** ou **[!UICONTROL Use existing adaptive form fragments]** une option à la fois. Vous ne pouvez pas utiliser les deux options simultanément.
   > * Vous pouvez utiliser cette **[!UICONTROL Use existing adaptive form fragments]** option uniquement avec les formulaires PDF non interactifs. Les autres types de formulaire ne sont pas encore pris en charge.
   > * Vous pouvez utiliser uniquement des fragments non liés ou des fragments liés à un JSON avec le service de conversion automatisé. N’utilisez pas de fragments XFA. Les fragments XFA ne sont pas pris en charge.


   * Sélectionnez l’ **[!UICONTROL Auto-detect multi-column layout of input forms]** option permettant de conserver la disposition du formulaire source pour les grands écrans tels que les ordinateurs de bureau et les ordinateurs portables. Cette option s’avère utile pour conserver la disposition à plusieurs colonnes des formulaires source. Par exemple, lorsqu’un fichier PDF source est doté d’une disposition à deux colonnes, le service génère un formulaire adaptatif de sortie avec une disposition à deux colonnes pour les grands écrans et une disposition à une seule colonne pour les périphériques de petit écran tels que les téléphones mobiles. Cette fonctionnalité présente des problèmes connus avec la structure  de la source de données. Pour plus d’informations, reportez-vous à l’article [known-issues](known-issues.md) .
   * Par défaut, le service crée un panneau de niveau supérieur distinct pour chaque page d’un formulaire PDF. Désormais, vous pouvez utiliser l’ **[!UICONTROL Auto-detect logical sections]** option pour ne pas créer de panneaux de niveau page (panneaux basés sur le numéro de page) et créer uniquement des panneaux logiques. Il regroupe également les champs qui n’appartiennent à aucune section avec les sections logiques précédentes et les champs d’une section logique répartis sur deux pages adjacentes en une seule section logique. Par exemple, si certains champs d’une section logique se trouvent à la fin de la page 1 et que d’autres se trouvent au début de la page 2, tous ces champs sont regroupés en une seule section logique.

      >[!NOTE]
      > Vous avez besoin du connecteur package 1.1.38 ou version ultérieure pour utiliser la **[!UICONTROL Auto-detect logical sections]** fonctionnalité.



1. Appuyer **[!UICONTROL Start Conversion]**. La conversion est lancée. La progression de la conversion s’affiche dans le dossier ou le formulaire jusqu’à ce que la conversion soit en cours. Le message est remplacé par un autre message d’état (Converti, Partiellement converti ou Echec de conversion) une fois la conversion terminée. Un courrier électronique d’état est également envoyé à l’adresse électronique configurée à la fin de la conversion :

   * Lors d’une conversion réussie, le formulaire adaptatif converti et les  connexes sont téléchargés vers le chemin spécifié dans l’ **[!UICONTROL Basic]** onglet de la boîte de dialogue de conversion. Les fragments de formulaire et les  correspondants ne sont téléchargés que si l’option Extraire le fragment est sélectionnée avant de commencer la conversion.
   * En cas d’échec de la conversion, le **[!UICONTROL Conversion Failed]** message s’affiche si tous les formulaires d’entrée ne sont pas convertis ou si le **[!UICONTROL Partially Failed]** message s’affiche lorsque seuls quelques-uns des formulaires d’entrée ne sont pas convertis. Un courrier électronique d’état est envoyé sur l’adresse [de courriel](configure-service.md#configureemailnotification) configurée et une erreur est consignée dans le fichier error.log.
   Si vous convertissez un formulaire PDF XFA en formulaire adaptatif, le service de conversion associe automatiquement le formulaire PDF au formulaire adaptatif converti comme modèle de  d’enregistrement. Après la conversion, vous pouvez ouvrir les propriétés du formulaire adaptatif pour  modèle de d’enregistrement dans la **[!UICONTROL Document of Record Template Configuration]** section de **[!UICONTROL Form Model]** l’onglet. </br>

   Le service de conversion télécharge automatiquement le formulaire PDF vers le formulaire adaptatif converti en tant que modèle de  d’enregistrement uniquement si vous activez l’option **[!UICONTROL Tools]** > **[!UICONTROL Cloud Services]** > **[!UICONTROL Automated Forms Conversion Configuration]** > **[!UICONTROL Properties of selected configuration]** > **[!UICONTROL Advanced]** > **[!UICONTROL Generate Document of Record]** .

   <!--
   Comment Type: draft

   <note type="note">
   <p>By default, the adaptive form produces a JSON schema instead of XML schema on submission. JSON schema of a converted adaptive form is complaint with XML schema of an XFA-based form. You can use the <a href="https://sling.apache.org/apidocs/sling5/org/apache/sling/commons/json/xml/XML.html#toString">org.apache.sling.commons.json.xml API</a> to convert a JSON schema to XML schema. You can also use the following sample code for conversion:</p>
   <p><code class="code">import org.apache.sling.commons.json.JSONException;
   <discoiqbr /> import org.apache.sling.commons.json.JSONObject;
   <discoiqbr /> import org.apache.sling.commons.json.xml.XML;
   <discoiqbr />
   <discoiqbr /> public class ConversionUtils {
   <discoiqbr />
   <discoiqbr /> public static String jsonToXML(String jsonString) throws JSONException {
   <discoiqbr /> //https://sling.apache.org/apidocs/sling5/org/apache/sling/commons/json/xml/XML.html#toString(java.lang.Object)
   <discoiqbr /> //jar - http://maven.ibiblio.org/maven2/org/apache/sling/org.apache.sling.commons.json/2.0.18/
   <discoiqbr /> //Note: Need to extract boundData part before converting to XML
   <discoiqbr /> return XML.toString(new JSONObject(jsonString));
   <discoiqbr /> }
   <discoiqbr /> }</code><br /> </p>
   </note>
   -->

   >[!NOTE]
   >
   >Si le processus de conversion dure plus de 60 minutes et que le formulaire PDF n’est toujours pas converti en formulaire adaptatif, créez un dossier sur l’instance AEM Forms, téléchargez le formulaire PDF dans le dossier nouvellement créé, puis redémarrez la conversion.

## Vérification et correction des formulaires convertis {#review-and-correct-the-converted-forms}

Les formulaires du monde réel ont des exigences complexes en matière de capture de données. Une fois la conversion automatisée terminée, les clients peuvent vérifier la qualité de la conversion du formulaire et apporter les mises à jour nécessaires au formulaire. AEM Forms fournit un éditeur [de révision et correct](review-correct-ui-edited.md) pour effectuer les modifications requises. Il vous permet d’améliorer l’identification automatisée des champs de formulaire et de convertir les champs identifiés d’un type à un autre. Par exemple, vous pouvez identifier la disposition à deux colonnes d’un formulaire et modifier un champ automatiquement identifié comme bouton radio en champ de choix multiples.
