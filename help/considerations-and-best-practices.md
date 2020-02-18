---
title: '[NE PAS PUBLIER] Meilleures pratiques et considérations '
seo-title: '[NE PAS PUBLIER] Meilleures pratiques et considérations '
description: 'null'
seo-description: 'null'
page-status-flag: never-activated
uuid: c2821264-39e2-44f8-b234-835c46f33fd5
topic-tags: introduction
discoiquuid: b786e40a-202e-4e17-a2f5-1f77c46538c2
privatebeta: true
index: false
translation-type: tm+mt
source-git-commit: afe461baa5bcfc1106c16aae2d6a9c839ea675e8

---


# [NE PAS PUBLIER] Meilleures pratiques et considérations {#do-not-publish-best-practices-and-considerations}

Le service de conversion automatisée d’AEM Forms convertit un formulaire PDF en formulaire adaptatif. Le service utilise l’intelligence artificielle et des algorithmes d’apprentissage automatique pour comprendre la disposition et les champs du formulaire source. Chaque service d’apprentissage automatique apprend en permanence des données source et produit une sortie améliorée à chaque exécution. Ces services apprennent de l&#39;expérience comme les humains.

Le service de conversion automatisée des formulaires est formé sur un grand ensemble de formulaires. Il identifie facilement les champs d’un formulaire source et génère des formulaires adaptatifs. Cependant, certains champs et styles des formulaires PDF sont facilement visibles à l’oeil humain mais difficiles à comprendre pour le service. Le service peut affecter des types de champs ou des panneaux différents de ceux applicables à certains champs ou styles. Tous ces modèles de champ et de style sont répertoriés ci-dessous.

Le service commencerait à identifier et à affecter des champs ou des panneaux corrects à ces modèles car il continuerait à apprendre des données source. Pour le moment, vous pouvez utiliser [l’éditeur Révision et Correct](review-correct-ui-edited.md) pour résoudre ces problèmes. Avant de commencer à résoudre les problèmes ou à lire davantage, familiarisez-vous avec les composants [de formulaire](https://helpx.adobe.com/experience-manager/6-5/forms/using/introduction-forms-authoring.html)adaptatif.

## Général {#general}

<!--
Comment Type: draft

<ul>
<li>Service does not convert filled PDF forms to adaptive form. Use empty adaptive forms.Service does not convert colored PDF forms to adaptive form. Use black and white or grayscale adaptive forms. <br /> </li>
<li>Service does not convert filled PDF forms to adaptive form. Use empty adaptive forms.</li>
<li>Service does not support scanned forms. Do not use scanned forms. </li>
<li>Service can fail to recognize text and fields in a dense form. Increase the width between text and fields of a dense form before starting the conversion.</li>
<li>Service does not extract images. Manually add images to converted forms.</li>
<li>Service does not extract text present within an image. Manually add text to the adaptive form.</li>
</ul>
-->

<table border="1" cellpadding="1" cellspacing="0" style="border-collapse: separate; border-spacing: 0px;" width="100%"> 
 <tbody>
  <tr>
   <td width="30%">Formats et résolution connus</td> 
   <td width="70%">Exemple</td> 
  </tr>
  <tr>
   <td><p><strong>Modèle</strong></p> <p>Le service ne convertit pas les formulaires PDF colorés en formulaires adaptatifs.</p> <p> </p> <p><strong>Résolution</strong></p> <p>Utilisez des formulaires PDF en noir et blanc ou en niveaux de gris. </p> </td> 
   <td style="text-align: left;"> <img src="assets/coloured-form.png" /></td> 
  </tr>
  <tr>
   <td><p><strong>Modèle</strong></p> <p>Le service ne convertit pas les formulaires PDF remplis en formulaire adaptatif.</p> <p> </p> <p><strong>Résolution</strong></p> <p>Utilisez des formulaires adaptatifs vides.</p> </td> 
   <td style="text-align: left;"><img src="assets/pre-filled-form.png" /></td> 
  </tr>
  <tr>
   <td><p><strong>Modèle</strong></p> <p>Le service peut ne pas reconnaître le texte et les champs sous une forme dense.</p> <p> </p> <p><strong>Résolution</strong></p> <p>Augmentez la largeur entre le texte et les champs d’un formulaire dense avant de commencer la conversion.</p> </td> 
   <td style="text-align: left;"><img src="assets/dense%20form.png" /></td> 
  </tr>
  <tr>
   <td><p><strong>Modèle</strong></p> <p>Le service ne prend pas en charge les formulaires numérisés.</p> <p> </p> <p><strong>Résolution</strong></p> <p>N’utilisez pas de formulaires numérisés. </p> </td> 
   <td><img src="assets/scanned-form.jpg" /></td> 
  </tr>
  <tr>
   <td><p><strong>Modèle</strong></p> <p>Le service n’extrait pas les images et le texte dans les images. </p> <p> </p> <p><strong>Résolution</strong></p> <p>Ajoutez manuellement des images ou du texte aux formulaires convertis.</p> </td> 
   <td><img src="assets/image-in-adaptive-form.png" /></td> 
  </tr>
  <tr>
   <td><p><strong>Modèle</strong></p> <p>Les tableaux avec des bordures et des bordures en pointillés ou non clairs ne sont pas convertis.</p> <p><strong>Résolution</strong></p> <p>Utilisez des tableaux avec des limites et des bordures explicites claires. pris en charge.</p> </td> 
   <td><img src="assets/border-less-tables.png" /></td> 
  </tr>
 </tbody>
</table>

## Groupe de choix {#choice-group}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td width="30%">Modèle</td> 
   <td width="70%">Exemple</td> 
  </tr>
  <tr>
   <td><p><strong>Modèle</strong></p> <p>Les options de groupe de choix avec des formes autres que la zone ou le cercle ne sont pas converties en composants de formulaire adaptatif correspondants. </p> <p> </p> <p><strong>Résolution</strong></p> <p>Modifiez les formes d’options de choix en une zone ou un cercle ou utilisez l’éditeur de révision et de correction pour identifier les formes.</p> </td> 
   <td><img src="assets/shaded-box-patterns.png" /> </td> 
  </tr>
 </tbody>
</table>

## Form fields {#form-fields}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td width="30%">Modèle</td> 
   <td width="70%">Exemple</td> 
  </tr>
  <tr>
   <td width="25%"><p><strong>Modèle</strong></p> <p>Le service n’identifie pas les champs sans bordures claires.</p> <p> </p> <p><strong>Résolution</strong></p> <p>Utilisez l’éditeur Révision et Correct pour identifier ces champs.</p> <p> </p> <p> </p> </td> 
   <td width="50%"><br /> <img src="assets/fields-without-clear-borders.png" /></td> 
  </tr>
  <tr>
   <td><p><strong>Modèle</strong></p> <p>Le service laisse certains champs de formulaire avec des légendes en bas ou à droite non identifiées.</p> <p> </p> <p><strong>Résolution</strong></p> <p>Utilisez l’éditeur Révision et Correct pour identifier ces champs.</p> </td> 
   <td><br /> <img src="assets/forms-with-clear-borders-scale.png" /><br /> </td> 
  </tr>
  <tr>
   <td><p><strong>Modèle</strong></p> <p>Le service fusionne ou affecte un type incorrect à certains champs de formulaire qui sont placés très près les uns des autres ou qui ne sont pas dotés de bordures claires. </p> <p> </p> <p><strong>Résolution</strong></p> <p>Utilisez l’éditeur Révision et Correct pour identifier ces champs.</p> </td> 
   <td><img src="assets/forms-with-fields-placed-nearby.png" /></td> 
  </tr>
  <tr>
   <td><p><strong>Modèle</strong></p> <p>Le service peut ne pas reconnaître les champs avec des légendes lointaines ou une ligne en pointillé entre la légende et le champ de saisie.</p> <p> </p> <p><strong>Résolution</strong></p> <p>Utilisez les champs de formulaire avec des limites claires ou utilisez l’éditeur Réviser et Corriger pour résoudre ces problèmes.</p> </td> 
   <td><img src="assets/form-fields-with-far-away-captions.png" /></td> 
  </tr>
 </tbody>
</table>

## Listes {#lists}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td width="30%">Modèle</td> 
   <td width="70%">Exemple</td> 
  </tr>
  <tr>
   <td><p><strong>Modèle</strong></p> <p>Les listes contenant des champs de formulaire sont fusionnées ou non converties en composants de formulaire adaptatif correspondants.</p> <p><strong>Résolution</strong></p> <p>Utilisez les champs de formulaire avec des limites claires ou utilisez l’éditeur Réviser et Corriger pour résoudre ces problèmes.</p> </td> 
   <td><img src="assets/lists-with-fields.png" /></td> 
  </tr>
  <tr>
   <td><p><strong>Modèle</strong></p> <p>Le service peut laisser quelques listes imbriquées non identifiées</p> <p> </p> <p><strong>Résolution</strong></p> <p>Utilisez l’éditeur Révision et Correct pour résoudre ces problèmes.</p> </td> 
   <td><img src="assets/nested-lists.png" /> </td> 
  </tr>
  <tr>
   <td><p><strong>Modèle</strong></p> <p>Le service fusionne certaines listes contenant des groupes de choix les unes avec les autres</p> <p><strong>Résolution</strong></p> <p>Utilisez l’éditeur Révision et Correct pour résoudre ces problèmes.</p> </td> 
   <td><img src="assets/lists-containing-choice-groups.png" /> </td> 
  </tr>
 </tbody>
</table>

<!--
Comment Type: draft

<h3>Choice groups</h3>
-->

<!--
Comment Type: draft

<ul>
<li>Lists with form fields, nested lists, and nested choice groups are not supported.</li>
<li>Form fields with captions at bottom or right are not supported.</li>
<li>Form fiields without bordes are not supported.</li>
<li>Hidden form fields are not supported.</li>
<li>Button in PDF forms are not converted to adaptive form buttons.<br /> </li>
<li>Tables with clear explicit boundaries and borders are supported.</li>
<li>Fields with far away captions are not supported.<br /> </li>
<li>Choice groups with only box or circle shaped selectors are supported. </li>
</ul>
-->

