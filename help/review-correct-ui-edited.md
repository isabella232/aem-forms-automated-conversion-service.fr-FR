---
title: Vérification et correction des formulaires convertis
seo-title: Vérification et correction des formulaires convertis
description: Examinez et corrigez les formulaires adaptatifs convertis par le service de conversion automatisée des formulaires.
seo-description: Vérifier et corriger les formulaires adaptatifs convertis par le service de conversion automatisée des formulaires
uuid: 5a0a6d24-dff6-4732-b607-24848b07b26d
topic-tags: forms
discoiquuid: f45ab2d7-5234-42d6-aeb6-b2cb1a7ce3c2
translation-type: tm+mt
source-git-commit: 3303c72b7d644dd183c036ba3cc48e629a9a503e

---


# Vérification et correction des formulaires convertis{#review-and-correct-converted-forms}

Le service de conversion automatisée des formulaires AEM Forms identifie les champs, le contenu et la disposition du document PDF d’entrée et convertit le document PDF en formulaire adaptatif. Le formulaire adaptatif de sortie peut comporter quelques champs manquants ou mal convertis. Vous pouvez utiliser l’éditeur Révision et Correct pour apporter des améliorations aux champs identifiés et régénérer le formulaire adaptatif afin de rapprocher une sortie de l’expérience souhaitée. Après la première conversion, vous pouvez ouvrir le document PDF d’entrée dans l’éditeur pour :

* Afficher tous les champs et le contenu identifiés lors de la conversion
* Identifier les champs et le contenu manqués pendant la conversion
* Vérifiez le type d’un champ et modifiez son type, le cas échéant.
* Vérifier les tableaux identifiés, redimensionner les colonnes et modifier le contenu des cellules
* Supprimer les champs mal identifiés

Après avoir apporté les modifications requises, renvoyez les formulaires PDF au service de conversion. Lors d’une conversion réussie, les actifs mis à jour, y compris le formulaire adaptatif et le schéma, sont téléchargés vers votre instance AEM Forms. Vous pouvez répéter le processus jusqu’à ce que l’expérience souhaitée soit réalisée. ![](assets/stages-of-form-2.gif)

Vous avez besoin du navigateur Google Chrome, Mozilla FireFox ou Microsoft Edge pour utiliser l’éditeur de révision et de correction. L’éditeur ne prend pas en charge Internet Explorer.

## Bienvenue dans l’éditeur Révision et correction {#welcome-to-review-and-correct-editor}

L’éditeur Révision et Correction offre une interface facile à utiliser. Il comporte les composants suivants :

* Explorateur de contenu : Vous pouvez utiliser l’explorateur de contenu pour modifier la position d’un élément. L’explorateur de contenu vous permet de faire glisser un objet de formulaire pour le modifier. Par exemple, en déplaçant un tableau avant une zone de texte. Il modifie l’ordre de tabulation du formulaire adaptatif de sortie en conséquence.
* Explorateur de propriétés : Il affiche les propriétés d’un champ sélectionné. Vous pouvez également modifier les propriétés.
* Barre d’outils : La barre d’outils se trouve en haut de l’éditeur. Il affiche des outils permettant d’ajouter, de modifier, de regrouper, de dissocier et de supprimer des champs.
* Propriétés d’ouverture : L’option Ouvrir les propriétés s’affiche lorsque vous appuyez sur l’ ![](assets/properties.png) icône. Vous pouvez cliquer sur Ouvrir les propriétés pour ouvrir les propriétés du formulaire et afficher d’autres options.
* Bouton Filtrer : Le bouton de filtre ![](assets/toggle_eye.png) se trouve en haut de l’éditeur. Il vous permet de filtrer les champs pour n’afficher que les textes, les champs, les groupes de choix, les panneaux ou tous les composants.
* Bouton Enregistrer : Le **[!UICONTROL Save]** bouton se trouve dans le coin supérieur droit de l’éditeur. Vous pouvez également utiliser la flèche en regard du bouton Enregistrer pour afficher l’option permettant d’envoyer le formulaire pour conversion.

* Formulaire PDF : L’éditeur affiche le document PDF source et le superpose avec les champs identifiés. Vous pouvez utiliser les outils de la barre d’outils pour modifier les champs.
* Pages : Un formulaire source peut comporter plusieurs pages. L’éditeur fournit un bouton dans le coin supérieur droit pour naviguer entre les pages.

![Interface utilisateur de révision et de correction](assets/reviewcorrectui.png)

**************A. Explorateur de contenu** B. Navigateur de propriétés **C.** Barre d’outils **D. Bouton Propriétés** E. Bouton Filtrer **F. Bouton Enregistrer** G. Formulaire PDF superposé avec des champs identifiés

Après la première conversion réussie, le service de conversion superpose le document PDF source avec les champs et composants identifiés. Ces champs ou composants sont de type : Texte, Champ, Panneau, Groupe de choix et tableau :

* Texte : Texte brut dans le document PDF source. Par exemple, le texte de la demande de prêt dans l’image affichée ci-dessus.
* Champ : Combinaison de texte ou d’étiquette d’icône associée à une valeur ou une zone de saisie. Par exemple, le nom du premier champ dans l’image ci-dessus. Il comporte un libellé de texte et une zone de saisie. Un champ prend en charge les types de données de texte, numérique, liste déroulante, date, courriel, numéro de téléphone, signature, devise et mot de passe.
* Panneau : Collection logique de contenu et de composants. Par exemple, les panneaux Détails personnels de la personne 1 et Personne 2 dans l’image ci-dessus.
* Groupe de choix : Combinaison de texte associée à plusieurs options de choix : case à cocher et bouton radio. Par exemple, Etat civil et client existant dans l’image ci-dessus.\
   En fonction de la légende du groupe de choix et de ses options à choix multiples, le service de conversion convertit automatiquement un groupe de choix en bouton radio à sélection unique ou en case à cocher à sélection multiple. Par exemple, s’il existe **Sélectionner une** légende de groupe de choix ou si les options à choix multiples vous permettent de sélectionner une seule option, **Oui** ou **Non**, le service de conversion convertit automatiquement le groupe de choix en bouton radio à sélection unique. De même, s’il existe **Sélectionner tout ce qui s’applique** ou **Sélectionner plusieurs** comme légende de groupe de choix ou comme les options à choix multiples vous permettent de sélectionner plusieurs options, le service de conversion convertit automatiquement le groupe de choix en case à cocher à sélection multiple.

* Tableau : Tableau 2d avec des informations représentées dans des colonnes et des lignes. Vous pouvez ajouter ou supprimer des lignes ou des colonnes à un tableau.

## Commencer à examiner une conversion {#start-reviewing-a-conversion}

Après la première conversion réussie, le service de conversion superpose le document PDF source avec les champs et composants identifiés. Vous pouvez apporter des améliorations aux champs identifiés et régénérer le formulaire adaptatif pour rapprocher une sortie de l’expérience souhaitée. Vous ne pouvez commencer à examiner une conversion qu’après la première conversion réussie.

### Avant de commencer {#before-you-start}

* L’éditeur de révision et de correction ne prend pas en charge les fragments. N’utilisez pas l’éditeur pour vérifier les conversions pour lesquelles l’option **Extraire le fragment** était activée pendant les conversions. Vous pouvez utiliser l’éditeur [de formulaires](https://helpx.adobe.com/experience-manager/6-5/forms/using/introduction-forms-authoring.html) adaptatifs pour de telles conversions.

* L’action Annuler ne s’applique pas à l’éditeur de révision et de correction. Utilisez le bouton Enregistrer uniquement pour enregistrer définitivement les modifications.

### Démarrage de la révision {#start-the-review}

Pour commencer à examiner les conversions, sélectionnez le document PDF source utilisé pour la conversion, puis sélectionnez et appuyez sur **Réviser les conversions**. L’éditeur Révision et Correction s’ouvre dans un nouvel onglet. Vous pouvez commencer à examiner les conversions. Effectuez les vérifications de base suivantes avant de commencer à résoudre un autre problème :

![](assets/usingreviewandcorrecteditor.png)

1. **Type de vérification de tous les champs**: Le service de conversion peut affecter un type incorrect à un champ. Par exemple, le texte de type est affecté au champ de téléphone mobile au lieu du téléphone. Vous pouvez pointer sur un champ pour trouver le type du champ.

   Pour modifier le type d’un champ, sélectionnez-le, ouvrez l’explorateur de propriétés, sélectionnez une valeur dans la **[!UICONTROL Type]** liste déroulante, puis appuyez sur **[!UICONTROL Save]**. Le type est modifié.

   ![](assets/check-typex75.gif)

1. **Supprimer les panneaux** supplémentaires : Le service de conversion peut générer des panneaux supplémentaires. Par exemple, un sous-panneau supplémentaire est inclus dans le panneau parent, un espace vide est converti en panneau, une case à cocher est convertie en panneau. Vérifiez les limites de tous les panneaux et supprimez les panneaux supplémentaires. Vous pouvez utiliser le ![](assets/toggle_eye.png) bouton de filtre ou l’explorateur de contenu pour afficher tous les panneaux.

   Vous pouvez supprimer ou dissocier un panneau pour le supprimer. Lorsque vous utilisez l’option de suppression, les champs enfants ou les composants du panneau sont également supprimés :

   * Pour supprimer un panneau, sélectionnez-le, puis appuyez sur l’icône Supprimer ![](assets/delete-icon.png) dans la barre d’outils. Dans la boîte de dialogue de confirmation, appuyez sur **[!UICONTROL Confirm]**. Tap **[!UICONTROL Save]** to save the changes.

   * Pour dissocier un panneau, sélectionnez-le, puis appuyez sur l’icône de dissociation dans la barre d’outils. Le panneau est dissocié et les champs enfants du panneau non regroupé sont ajustés au champ parent. Tap **[!UICONTROL Save]**to save the changes.

1. **Créez des groupes logiques de texte**: Validez les textes identifiés pour vérifier leur exhaustivité et leur exactitude. Vérifiez également que les textes sont logiquement placés dans des panneaux ou des groupes corrects. Par exemple, dans une disposition à colonnes multiples, les textes d’un groupe logique et placés dans un autre groupe.

   * Pour vérifier l’exhaustivité et l’exactitude du texte, utilisez le ![](assets/toggle_eye.png) bouton de filtre pour afficher uniquement le texte, cliquez sur chaque texte et validez. Correction des problèmes d’orthographe, de frappe ou de grammaire, le cas échéant.

   * Pour ajouter du texte au formulaire, appuyez sur le bouton +, puis sur **[!UICONTROL Text]**. Tracez la zone, ouvrez l’explorateur de propriétés et saisissez le texte à ajouter à la zone Contenu.

1. **** Vérifier les tableaux : Assurez-vous que toutes les bordures du tableau sont identifiées. Assurez-vous également que le contenu des cellules est correctement identifié.

   * Pour identifier les bordures manquantes, utilisez l’ **[!UICONTROL Add Column]** option ou **[!UICONTROL Add Row]** .

   * Pour supprimer des bordures supplémentaires, utilisez l’ **[!UICONTROL Delete Column]** option ou **[!UICONTROL Delete Row]** .

Après avoir apporté les modifications requises, appuyez sur le **[!UICONTROL Save & Convert]** bouton pour renvoyer les formulaires PDF au service de conversion. Chaque champ est converti en composant de champ adaptatif correspondant. Après la conversion, les actifs mis à jour, y compris le formulaire adaptatif et le schéma, sont téléchargés vers votre instance AEM Forms. Selon la complexité du formulaire, le service peut prendre un certain temps pour terminer la conversion.

![Enregistrer et convertir](assets/save-and-convert.png)

Après avoir effectué les vérifications de base, vous pouvez consulter le formulaire pour résoudre les problèmes spécifiques à votre organisation. Ces problèmes peuvent être liés à l’ajout de champs manquants, etc. Vous pouvez consulter la section [Utilisation des outils](review-correct-ui-edited.md#use-the-review-and-correct-editor-tools) d’éditeur de révision et de correction pour en savoir plus sur tous les outils fournis par l’éditeur pour résoudre ces problèmes.

Vous pouvez également identifier les problèmes identiques qui se produisent dans presque tous vos formulaires et signaler ces modèles à Adobe. Utilisez l’éditeur Réviser et Corriger jusqu’à ce que l’expérience souhaitée soit réalisée.

## Utilisation des outils de révision et de correction de l’éditeur {#use-the-review-and-correct-editor-tools}

Avec l’éditeur Révision et Correct, vous pouvez :

* [Ajouter un composant au formulaire](review-correct-ui-edited.md#add-a-component-to-the-form)
* [Ajout ou modification d’un tableau](review-correct-ui-edited.md)
* [Modification du type d’un composant](review-correct-ui-edited.md#change-type-a-component)

* [Création ou suppression d’un panneau](review-correct-ui-edited.md#create-or-remove-a-panel)
* [Suppression d’un panneau ou d’un composant](review-correct-ui-edited.md#delete-a-panel-or-component)
* [Définition des propriétés d’un composant](review-correct-ui-edited.md#set-properties-of-a-component)
* [Envoyer un formulaire pour conversion](review-correct-ui-edited.md#send-a-form-for-conversion)

### Ajouter un composant au formulaire {#add-a-component-to-the-form}

Le service de conversion peut ne pas identifier certains composants du formulaire imprimé. Par exemple, dans un composant **Date de naissance** d’un formulaire, il n’est pas identifié lors de la conversion. Vous pouvez utiliser l’outil **+** pour identifier ces composants. L’outil vous permet d’ajouter du texte, des champs, un groupe de choix, un tableau et des composants de panneau.

![](assets/add-component.gif)

Pour ajouter un composant au formulaire, appuyez **[!UICONTROL +]** et appuyez sur **[!UICONTROL Field]**. Tracez une zone de libellé et une zone de saisie du champ. Par exemple, l’exemple d’image ci-dessus utilise le composant de champ pour ajouter au formulaire l’étiquette **Date de naissance** et la zone de valeur située en dessous. Lorsque vous tracez la zone, le service de conversion identifie le type du champ. Vous pouvez modifier le type de champ à partir du navigateur de propriétés, le cas échéant. Après avoir créé le composant, ouvrez l’explorateur de propriétés et définissez ses propriétés.

Appuyez sur **[!UICONTROL Save]** le bouton pour enregistrer les modifications ou utilisez le **[!UICONTROL Save & Convert]** bouton pour renvoyer les formulaires PDF au service de conversion.

### Ajout ou modification d’un tableau {#addedittable}

La conversion peut laisser quelques cellules, limites ou contenu d’une cellule de tableau non identifiés. Par exemple, une ligne d’un tableau n’est pas identifiée. Vous pouvez utiliser l’éditeur Révision et correction pour identifier ces éléments. Vous pouvez exécuter les actions suivantes pour un tableau :

* Pour sélectionner un tableau, cliquez sur une cellule du tableau.
* Pour modifier les propriétés d’une cellule, telles que son nom, son titre ou son type, double-cliquez sur une cellule. Vous pouvez également cliquer deux fois sur la cellule pour modifier le contenu, marquer un champ obligatoire et sélectionner d’autres propriétés.
* Pour ajouter/identifier un tableau entièrement non identifié ou un nouveau tableau dans le formulaire, utilisez l’ **[!UICONTROL +]** outil.
* Pour redimensionner des cellules ou des rangées d’un tableau, cliquez une fois sur la zone vide du tableau, passez la souris sur la bordure de la rangée ou de la colonne, puis sélectionnez et déplacez la bordure lorsque le pointeur du curseur change. Après avoir redimensionné, cliquez **[!UICONTROL Done]** pour valider les modifications. Vous pouvez appuyer sur la **[!UICONTROL ESC]** touche pour ignorer le redimensionnement.

* Pour ajouter ou supprimer des lignes ou des colonnes, sélectionnez une cellule dans la rangée du tableau, puis sélectionnez l’option **[!UICONTROL Add Row]**, **[!UICONTROL Add Column]**, **[!UICONTROL Delete Row]** ou **[!UICONTROL Delete Column]** dans le ![](assets/table_18x18.png) menu.

* Pour scinder une cellule d’un tableau, sélectionnez l’option **[!UICONTROL Spilt Vertical]** ou **[!UICONTROL Split Horizontal]** dans le ![](assets/table_18x18.png) menu.

* Pour fusionner des cellules d’un tableau, sélectionnez les cellules à fusionner, puis sélectionnez l’ **[!UICONTROL Merge Cells]** option dans le menu du ![](assets/table_18x18.png) tableau.

### Modification du type d’un composant {#change-type-a-component}

Le service de conversion peut créer des champs de type incorrect. Par exemple, dans l’image suivante, le champ **Sexe** est incorrectement identifié comme un champ de **texte** . En outre, le contenu du libellé est incorrect. Le champ doit être un type de champ de choix et l’étiquette doit être Sexe. Pour modifier le type d’un composant et corriger son étiquette :

Sélectionnez le champ à convertir, appuyez sur ![](assets/smock_shuffle_18_n.svg) et appuyez sur un type de champ. Le champ est converti en type de champ sélectionné. Un champ peut uniquement être converti en types répertoriés dans le tableau suivant. Un composant de panneau peut uniquement être dissocié, et non transformé.

| **Component** | **Convertit en** |
|---|---|
| Texte | Champ ou Groupe de choix |
| Champ | Texte ou Groupe de choix |
| Groupe de choix | Texte ou panneau |

Une fois la conversion terminée, ouvrez le navigateur de propriétés, spécifiez une étiquette et spécifiez d’autres propriétés requises. Appuyez sur **[!UICONTROL Save]** le bouton pour enregistrer les modifications ou utilisez le bouton Enregistrer et convertir pour renvoyer les formulaires PDF au service de conversion.

### Création ou suppression d’un panneau {#create-or-remove-a-panel}

Le service de conversion regroupe les composants et le contenu connexes des formulaires d’impression dans un panneau. Par exemple, le formulaire peut comporter un panneau d’adresse avec des champs tels que, nom, numéro de graphique, zone, ville, état, code postal et pays. Ces champs sont regroupés dans un panneau. Un formulaire peut comporter plusieurs panneaux.

Le service de conversion peut créer des panneaux qui ont des composants sans rapport avec d’autres ou qui laissent un composant relatif hors du panneau. Vous pouvez utiliser les outils de groupe ou de dissociation pour réparer ces panneaux :

* Pour supprimer un panneau, sélectionnez-le, puis appuyez sur Dissocier ![le groupe](assets/ungroupX18.png). Le panneau est supprimé et les composants enfants du panneau sont déplacés vers le composant parent. Vous pouvez également utiliser l’option [Supprimer le composant](review-correct-ui-edited.md#delete-a-panel-or-component) pour supprimer un panneau et ses enfants.

* Pour créer un panneau, utilisez la touche Ctrl (sous Windows ou Linux) ou Ctrl (sous Mac) pour sélectionner les composants associés, puis appuyez sur ![le groupe](assets/group.jpg) pour créer un panneau. Ouvrez l’explorateur de propriétés pour spécifier les propriétés du panneau.

Appuyez sur **[!UICONTROL Save]** le bouton pour enregistrer les modifications ou utilisez le **[!UICONTROL Save & Convert]** bouton pour renvoyer les formulaires PDF au service de conversion.

### Suppression d’un panneau ou d’un composant {#delete-a-panel-or-component}

Le service de conversion peut identifier certains panneaux ou composants incorrects. La plupart de ces éléments de ces panneaux ne sont pas liés. Vous pouvez supprimer ces panneaux ou composants.

Pour supprimer un panneau ou un composant, sélectionnez un panneau ou un composant, puis appuyez sur l’icône Supprimer ![](assets/delete-icon.png) . Dans la boîte de dialogue de confirmation, appuyez sur **[!UICONTROL Confirm]**. Le panneau ou le composant sélectionné est supprimé. Lors de la suppression d’un panneau, tous les enfants du panneau sont également supprimés. Vous pouvez utiliser la touche Ctrl (sous Windows ou Linux) ou Ctrl (sous Mac) pour sélectionner plusieurs composants ou panneaux.

### Définition des propriétés d’un composant {#set-properties-of-a-component}

Chaque composant du formulaire possède un ensemble de propriétés telles que nom, titre, type. Pour définir les propriétés d’un composant, sélectionnez-le, puis appuyez sur l’explorateur de propriétés. Les propriétés du composant sélectionné s’affichent. Modifiez ou définissez les propriétés.

Appuyez sur **[!UICONTROL Save]** le bouton pour enregistrer les modifications ou utilisez le **[!UICONTROL Save & Convert]** bouton pour renvoyer les formulaires PDF au service de conversion.

### Envoyer un formulaire pour conversion {#send-a-form-for-conversion}

Une fois toutes les modifications requises effectuées dans l’éditeur Révision et Correct, vous pouvez renvoyer le formulaire pour conversion. Pour envoyer le formulaire à des fins de conversion, appuyez sur **[!UICONTROL Save & Convert]**. Le **[!UICONTROL Sent for conversion label]** est appliqué au dossier contenant le document source et le formulaire source mis à jour est téléchargé vers le service de conversion s’exécutant sur les E/S Adobe.

Selon la complexité du formulaire, le service de conversion peut prendre un certain temps pour convertir le formulaire. Une fois la conversion terminée, le formulaire adaptatif converti et les ressources associées sont téléchargés sur votre ordinateur. Vous pouvez consulter le formulaire dans l’éditeur une fois la conversion terminée et ouvrir le formulaire adaptatif dans l’éditeur [de formulaires](https://helpx.adobe.com/experience-manager/6-5/forms/using/introduction-forms-authoring.html) adaptatifs pour le jeu final de correctifs, le cas échéant.

Si vous renvoyez un formulaire à des fins de conversion après la mise à jour du formulaire dans l’éditeur de formulaires adaptatifs, toutes les modifications apportées au formulaire adaptatif sont perdues. Vous pouvez ouvrir un formulaire dans un éditeur de révision et de correction uniquement après une conversion réussie.

<!--
Comment Type: draft

<h3>Open adaptive forms editor</h3>
-->

<!--
Comment Type: draft

<p>There can be instances where you require adaptive forms editor to make the changes like, applying a different theme to the form or fixing tables. Once you have made all the required changes in Review and Correct editor and converted the form, you can open your form in adaptive forms editor to make the final set of changes.</p>
<p>To open the form with adaptive forms editor, tap the <img src="assets/properties.png" /> icon, and tap <strong>Open Adaptive Form Editor</strong>. The form opens in adaptive form editor. </p>


## Previous {#previous}

[Use Automated Forms Conversion service](convert-existing-forms-to-adaptive-forms.md)
