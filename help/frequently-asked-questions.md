---
title: Forum aux questions
seo-title: Forum aux questions
description: Requêtes courantes ou questions fréquentes
seo-description: questions fréquentes sur le service de conversion automatisée des formulaires
uuid: 0f6dc39c-99b7-49a4-8e9e-ecc4a35110c0
topic-tags: introduction
discoiquuid: e17c2d2c-8300-4467-aa01-57365697939f
translation-type: tm+mt
source-git-commit: 1e22587a832ca8d09f33141a9ba4e4b1748e0312

---


# Forum aux questions{#frequently-asked-questions}

1. **Quelle version d’AEM Forms le service de conversion automatisée des formulaires prend-il en charge ?**
   <p>Le service de conversion automatisée des formulaires prend en charge AEM Forms 6.5. Il fonctionne avec AEM Forms sur OSGi et AEM Forms sur JEE. Vous avez besoin du dernier package de module complémentaire AEM Forms sur l’instance d’auteur AEM pour utiliser le service. Pour obtenir des instructions détaillées, voir <a href="configure-service.md">Configuration du service de conversion</a> automatisée des formulaires.</p> 
    <br>

1. **Le service peut-il être installé sur site ?**
   <p>Adobe forme régulièrement les algorithmes AI et ML du service de conversion automatisée des formulaires avec de nouvelles données pour améliorer la précision des conversions. Les algorithmes mis à jour sont déployés périodiquement sur le service de conversion s’exécutant sur Adobe Cloud. Tous les clients du service bénéficient des algorithmes mis à jour. Ainsi, le déploiement central hébergé dans le cloud est mieux adapté pour que le service de conversion automatisée des formulaires puisse apprendre en permanence et apporter des améliorations à tous les clients.</p> 
    <p>Le service convertit des formulaires vierges en formulaires adaptatifs. Le service ne prend pas en charge les formulaires remplis et l’extraction des données des formulaires remplis. Supprimez les données des formulaires remplis et supprimez ou placez les informations propriétaires de la liste blanche des formulaires avant d’envoyer les formulaires au service en vue de les convertir.</p> <br>

1. **Le service prend-il en charge tous les formats de formulaires PDF ? Quelles sont les langues prises en charge ?**
   <p>Le service peut convertir des formulaires PDF non interactifs, des formulaires XDP et PDF basés sur XFA et des formulaires AcroForms en formulaires adaptatifs. Le service ne prend pas en charge les formulaires numérisés ou remplis. Pour connaître d’autres restrictions, reportez-vous à l’article Problèmes <a href="known-issues.md"></a> connus.<br /> </p> 
    <p>Nous ajoutons régulièrement la prise en charge d'autres types de sources. Conservez la section Formulaires <a href="introduction.md">PDF</a> pris en charge dans votre liste de contrôle pour une mise à jour régulière des nouvelles fonctionnalités et fonctionnalités ajoutées.</p>

   Le service peut convertir uniquement des formulaires en anglais en formulaires adaptatifs. Vous pouvez traduire les formulaires adaptatifs générés dans une autre langue à l’aide du processus de traduction [AEM.](https://helpx.adobe.com/experience-manager/6-5/forms/using/using-aem-translation-workflow-to-localize-adaptive-forms.html)</br> </br>

1. **Le service peut-il produire un fichier XDP au lieu d’un formulaire adaptatif ?**
   <p>Le service ne produit pas de sortie XDP. Nous ajoutons régulièrement des fonctionnalités et des fonctionnalités au service. Conservez la section Langues <a href="introduction.md">prises en charge et Formulaires</a> PDF dans votre liste de contrôle pour une mise à jour régulière des nouvelles fonctionnalités et fonctionnalités ajoutées.</p> <br>

1. **Quel est le type du schéma généré ?**
   <p>Vous pouvez utiliser le service pour générer : </p>

   * un formulaire adaptatif lié à un schéma JSON et
   * un formulaire adaptatif non lié à un schéma <br><br>

1. **Le service peut-il convertir un formulaire Microsoft Word en formulaires adaptatifs ?**
   <p>Non, le service ne convertit pas un formulaire Microsoft Word en formulaire adaptatif. Vous pouvez enregistrer un formulaire Microsoft Word au format PDF et convertir le formulaire PDF en formulaire adaptatif. Le processus complet est </p> <br>

   1. Utilisez Adobe Acrobat pour [convertir un document Word au format PDF](https://helpx.adobe.com/acrobat/how-to/create-pdf-files-word-excel-website.html)non interactif.
   1. Utilisez Adobe Acrobat pour [convertir les formulaires PDF générés en formulaire](https://helpx.adobe.com/acrobat/how-to/convert-word-excel-paper-pdf-forms.html)PDF à remplir.
   1. Utilisez Adobe Acrobat pour mettre à jour et corriger manuellement les champs du formulaire.
   1. Enregistrez le formulaire PDF. Vous pouvez désormais utiliser le formulaire avec le service de conversion pour générer un formulaire adaptatif. Vous pouvez également utiliser le formulaire comme modèle de document d’enregistrement.


1. **Le service peut-il convertir des formulaires papier numérisés et des formulaires colorés en formulaires adaptatifs ?**
   <p>Le service peut convertir des formulaires PDF en formulaires adaptatifs. Le service ne prend pas en charge les formulaires numérisés ou remplis. Pour connaître d’autres restrictions, reportez-vous à l’article Problèmes <a href="known-issues.md"></a> connus.</p> <br>

1. **Le service peut-il convertir un formulaire numérisé ou uniquement l’image d’un formulaire en formulaire adaptatif ?**
   <p>Le service ne prend pas en charge la conversion de formulaires numérisés ou d’une image d’un formulaire en formulaire adaptatif prêt à l’emploi. Toutefois, vous utilisez Adobe Acrobat pour convertir l’image d’un formulaire en formulaire PDF. Utilisez ensuite le service pour convertir le formulaire PDF en formulaire adaptatif. Utilisez toujours une image de haute qualité du formulaire pour la conversion dans Acrobat. Elle améliore la qualité de la conversion.</p> <br>

1. **Certains formulaires XDP utilisent des fragments de formulaire, où ces fragments de formulaire doivent-ils être téléchargés ?**
   <p class="MsoNormal">Téléchargez des fragments de formulaire dans le dossier de conversion et conservez la structure de dossiers d’origine. Elle permet de conserver les chemins relatifs utilisés dans les formulaires XDP et les fragments de formulaire.</p> <br>

1. **Le service prend-il en charge les formulaires XDP liés au schéma ? Si j’ai un fichier XDP lié à un schéma, dois-je incorporer le schéma au fichier XDP ?**
   <p>Oui, le service prend en charge les formulaires XDP liés aux schémas et requiert que le schéma soit incorporé au formulaire XDP source. Lorsque vous convertissez un formulaire XDP lié au schéma, le service génère un schéma JSON. Le schéma JSON est structurellement similaire au schéma XSD des formulaires XDP source.</p> <br>

1. **Le service n’a pas pu convertir les formulaires. Quelle est la raison et comment résoudre le problème?**
Les raisons les plus courantes de l’échec de la conversion sont les suivantes :</p>
   * Les formulaires PDF sécurisés sont fournis pour la conversion. N’utilisez pas de formulaires PDF protégés par mot de passe ou sécurisés pour la conversion.
   * Connexion Internet interrompue. Vérifiez que vous êtes connecté à Internet pendant la conversion.
   * Le PDF source contient une image du formulaire au lieu du formulaire réel.
   * Le service est mal configuré, l’URL du service n’est pas fournie ou l’URL du service fourni est incorrecte. Vérifiez la configuration [du](configure-service.md#configure-the-cloud-service) service dans **[!UICONTROL AEM]** > **[!UICONTROL Tools]** > **[!UICONTROL Cloud Services]** > **[!UICONTROL Automated Forms Conversion configuration]**.
   * La configuration IMS n&#39;est pas configurée correctement. Effectuez un contrôle d’intégrité sur la configuration IMS pour vous assurer qu’elle fonctionne correctement. Pour vérifier si la configuration IMS est correcte ou non :
      1. Aller à `http://[servername]:[port]/libs/cq/adobeims-configuration/content/configurations.html`
      2. Sélectionnez la configuration. Cliquez sur le **[!UICONTROL Check Health]** dans l’en-tête, puis sur **[!UICONTROL Check]**. En cas de succès, vous recevez un **[!UICONTROL Token retrieved successfully!]** message. <br> <br>

1. **L’utilisation de polices personnalisées a-t-elle un impact sur la conversion ?**
   <p>Lorsqu’un formulaire PDF non interactif est converti en formulaire adaptatif, pour améliorer la qualité de la conversion, les polices sont incorporées dans le formulaire PDF. La prise en charge de l’incorporation de polices est limitée aux formulaires PDF non interactifs. Pour optimiser la conversion des formulaires PDF AcroForm et XFA, des polices de secours sont utilisées.</p> 
    <p>Seuls les formulaires disponibles dans le répertoire des polices personnalisées répertoriés dans le champ Répertoire <strong>des polices du</strong> client de la configuration du service <strong></strong> Gestionnaire de polices CQ-DAM-Handler-Gibson sont incorporés dans un formulaire PDF non interactif.</p> 
    <p> </p> <br>

1. **Le service identifie-t-il et utilise-t-il les polices du PDF source dans les formulaires adaptatifs de sortie ?**
   <p>Le style et la disposition d’un formulaire HTML dynamique sont généralement différents d’un formulaire PDF ou papier. Pour prendre en charge une disposition et un style cohérents dans toutes les organisations, les formulaires adaptatifs utilisent <a href="https://helpx.adobe.com/experience-manager/6-5/forms/using/themes.html">des thèmes pour mettre en forme un formulaire</a>. Le service de conversion utilise les polices et les styles de police spécifiés dans le thème appliqué pendant la conversion. Vous pouvez modifier les polices et les styles de police du thème pour donner une apparence distincte aux composants d’un formulaire adaptatif.</p> <br>

1. **Le service extrait-il automatiquement JavaScript des formulaires XDP et l’applique-t-il aux formulaires adaptatifs correspondants ?**
   <p>Le service ne convertit pas automatiquement les scripts de formulaires XFA ou de formulaires Acro en règles de formulaire adaptatif correspondantes. Vous (auteurs de formulaires) pouvez utiliser l’éditeur <a href="https://helpx.adobe.com/experience-manager/6-5/forms/using/rule-editor.html">de</a> règles pour ajouter de l’interactivité à un formulaire adaptatif.</p> <br>

1. **Certains objets de formulaire ne sont pas correctement convertis en composants de formulaire adaptatif. How to resolve the issue?**
   <p>Le service de conversion automatisée des formulaires est formé sur un grand ensemble de formulaires. Mais les applications basées sur AI/ML sont limitées par leurs données et leurs schémas de formation. Il pourrait y avoir plusieurs types de champs, mises en page, modèles et contexte visibles par la perception humaine, mais difficiles à reconnaître automatiquement. Le service peut ne pas identifier ces objets ou ne pas les reconnaître correctement. Vous pouvez utiliser l’éditeur <a href="review-correct-ui-edited.md" target="_blank">de révision et de correction</a> pour apporter les modifications nécessaires à la disposition courante du formulaire d’entrée sur papier.</p> <br/>

1. **Certaines corrections sont répétées dans les formulaires. Le service peut-il identifier et réparer toutes ces instances dans les conversions futures ?**

   Le service assure une formation cohérente sur vos formulaires et modèles. Il apprend de nouveaux modèles au quotidien. Il n’est pas encore possible de commencer à appliquer automatiquement les corrections répétées dans les formulaires. Gardez un oeil sur les formulaires de pré-version pour la disponibilité d&#39;une telle fonctionnalité. <br/><br/>

   Vous pouvez utiliser le méta-modèle pour mapper les objets de formulaire au composant de formulaire adaptatif de votre choix et préconfigurer les validations, les règles, les modèles de données, le texte d’aide et les propriétés d’accessibilité pour les composants. Toutes les propriétés spécifiées sont appliquées pendant la conversion. Vous pouvez utiliser le méta-modèle pour appliquer des propriétés courantes aux champs. Cela peut vous aider à réduire certains problèmes répétés dans les formulaires.<br/><br/>

1. **Quelles sont les options pour les formulaires contenant des données sensibles comme les informations d’identification personnelle (informations d’identification personnelle) ?**
Le service ne prend en charge que les formulaires vides ou non remplis. Ne transférez pas les formulaires remplis ou les formulaires contenant des informations d’identification personnelle. Supprimez également les données préremplies et les informations d’identification personnelle de marque blanche, confidentielles et exclusives dans les formulaires source. <br/>

1. **Où placer l’en-tête et les pieds de page ?**
   <p>Placez l’en-tête et le pied de page dans un modèle de formulaires adaptatifs. Si le formulaire PDF source comporte un en-tête et un pied de page, le service détecte et remplace l’en-tête et le pied de page détectés par l’en-tête et le pied de page disponibles dans le modèle de formulaire adaptatif pendant la conversion. Si un en-tête ou un pied de page supplémentaire est inclus dans le formulaire adaptatif, vous pouvez utiliser l’éditeur <a href="review-correct-ui-edited.md">de révision et de correction</a> pour corriger ou supprimer cet en-tête ou ce pied de page.</p> <br />

1. **Combien de temps le service économise-t-il par rapport au processus manuel de planification, de création d’actifs (thèmes, modèles), de création et de publication d’un formulaire adaptatif ?**
   <p>La durée dépend de la taille et de la complexité des formulaires d’entrée et du nombre de requêtes. Le service a l’intention de réduire considérablement le temps de conversion des formulaires PDF en formulaires adaptatifs à un rythme beaucoup plus rapide que le processus manuel de conversion des formulaires. </p> <br />

1. **Que faire si je rencontre une erreur liée aux bibliothèques RSA ?** Le message d’erreur est similaire au message mentionné ci-dessous : <br/>
   `*ERROR* [0:0:0:0:0:0:0:1 [1565757652491] POST /content/dam/formsanddocuments/demo004.affBatchProcessor.html HTTP/1.1] org.apache.sling.engine.impl.SlingRequestProcessorImpl service: Uncaught Throwable java.lang.NoClassDefFoundError: Could not initialize class com.rsa.cryptoj.o.dl at com.rsa.jsafe.JSAFE_SecureRandom.getInstance(Unknown Source) at com.adobe.internal.pdfm.util.Util.appendRandomNumberToPrefix(Util.java: 169) [com.adobe.aemfd.adobe-aemfd-assembler:6.0.34] at com.adobe.internal.pdfm.logging.JobLog.&amp;lt;init&amp;gt;(JobLog.java:126) [com.adobe.aemfd.adobe-aemfd-assembler:6.0.34]` <br>L&#39;erreur ci-dessus se produit lorsque la délégation de démarrage n&#39;est pas configurée pour les bibliothèques RSA/BouncyCastle. Pour résoudre le problème, procédez comme suit :
   <p> </p>

   1. Désactivez l’instance d’AEM. Navigate to the `[AEM installation directory]\crx-quickstart\conf\` folder. Ouvrez le fichier sling.properties pour le modifier. Si vous utilisez `[AEM installation directory]\crx-quickstart\bin\start.bat` pour démarrer une instance AEM, modifiez le fichier sling.properties situé dans `[AEM_root]\crx-quickstart\`.
   1. Ajoutez les propriétés suivantes au fichier sling.properties :<br/> `sling.bootdelegation.class.com.rsa.jsafe.provider.JsafeJCE=com.rsa.*`<br />  `sling.bootdelegation.class.org.bouncycastle.jce.provider.BouncyCastleProvider=org.bouncycastle.*`<br /> `sling.bootdelegation.xerces=org.apache.xerces.*`
   1. Enregistrez le fichier, puis fermez-le. <br/>
   1. Démarrez l’instance AEM.<br/>
   <br/>

1. **Comment modifier automatiquement l’enveloppe du texte du formulaire adaptatif ?**
   <p>Vous pouvez utiliser l’option adaptative à partir de thèmes ou d’un éditeur de style pour modifier le casse d’un champ de formulaire adaptatif. Par exemple, vous pouvez ouvrir l’éditeur de thème et définir la valeur de la propriété Case de tout le texte du formulaire sur majuscule, minuscule ou croustillant. Vous pouvez également utiliser l’option Remplacement CSS dans l’éditeur de thème pour créer différents types de styles.</p>