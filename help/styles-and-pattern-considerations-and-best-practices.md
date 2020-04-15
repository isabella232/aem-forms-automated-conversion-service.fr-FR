---
title: 'Bonnes pratiques et remarques '
seo-title: 'Bonnes pratiques et remarques '
description: Bonnes pratiques et remarques relatives au service de conversion automatisée de formulaires
seo-description: Liste des styles et des modèles dans les formulaires PDF sources que le service de conversion automatisée de formulaires a du mal à identifier
uuid: e24773a2-be14-4184-a168-48aa976d459a
topic-tags: introduction
discoiquuid: 79f2026e-73a5-4bd1-b041-d1399b4ad23e
translation-type: tm+mt
source-git-commit: 12b4df8feb19fdc6e723c4d7301d299f26676716

---


# Bonnes pratiques et modèles complexes connus {#Best-practices-and-considerations2}

Ce document fournit des instructions et des recommandations dont peuvent bénéficier l’administrateur, les auteurs et les développeurs de formulaires au moment d’utiliser le service de conversion automatisée de formulaires. Il décrit les bonnes pratiques, de la préparation des formulaires sources à la correction des modèles complexes qui nécessitent un effort supplémentaire pour la conversion automatisée. Ces meilleures pratiques contribuent collectivement aux performances et à la sortie globales du service de conversion automatisée des formulaires.

## Bonnes pratiques

Le service de conversion convertit les formulaires PDF disponibles sur votre instance AEM Forms en formulaires adaptatifs. Les meilleures pratiques répertoriées ci-dessous vous aident à améliorer la vitesse et la précision des conversions. En outre, ces bonnes pratiques vous aident à gagner du temps après  de conversion .

### Avant de télécharger des formulaires source
Vous pouvez télécharger tous les formulaires PDF en une seule ou en plusieurs fois, selon les besoins. Avant de télécharger les formulaires, tenez compte des éléments suivants :

* N’enregistrez pas plus de 15 formulaires dans un dossier et veillez à ce que le nombre total de pages dans un dossier ne dépasse pas 50.
* Veillez à ce que la taille du dossier ne dépasse pas 10 Mo. Ne conservez pas les formulaires dans un sous-dossier.
* Veillez à ce qu’un formulaire ne dépasse pas 15 pages.
* Organisez les  sources dans un lot de  de 8 à 15. Conservez les formulaires source avec des fragments de formulaire adaptatif courants dans un seul lot.
* Ne téléchargez pas de formulaires protégés. Le service ne convertit pas les formulaires protégés par mot de passe et sécurisés.
* Ne téléchargez pas de [portfolios PDF](https://helpx.adobe.com/fr/acrobat/using/overview-pdf-portfolios.html). Le service ne convertit pas un portfolio PDF en formulaire adaptatif.
* Ne transférez pas les formulaires numérisés, colorés, en langue autre que l’anglais et remplis. Ces types de formulaires ne sont pas pris en charge.
* Ne téléchargez pas de formulaires PDF sources dont le nom comporte des espaces. Supprimez l’espace du nom du fichier avant de télécharger les formulaires.

Lorsque vous utilisez un formulaire XDP pour la conversion, effectuez les étapes suivantes avant de télécharger les formulaires XPD source :

* Analysez le formulaire XDP et corrigez les problèmes visuels. Assurez-vous que le source utilise les contrôles et les structures prévus. Par exemple, le formulaire source peut comporter des cases à cocher au lieu de boutons radio pour une sélection unique. Remplacez les cases à cocher par des boutons radio pour produire un formulaire adaptatif avec les composants prévus.
* [Ajouter des liaisons au formulaire](http://www.adobe.com/go/learn_aemforms_designer_65) XDP avant de commencer la conversion. Lorsque des liaisons sont disponibles dans le formulaire XDP source, le service applique automatiquement des liaisons aux champs de formulaire adaptatif correspondants pendant la conversion. Cela vous permet de gagner du temps pour appliquer manuellement les liaisons.
* [Ajouter les balises](https://helpx.adobe.com/sign/using/text-tag.html) Adobe Sign au fichier XDP. Le service convertit automatiquement les balises Adobe Sign en champs de formulaire adaptatif correspondants. Les formulaires adaptatifs prennent en charge un nombre limité de champs Adobe Sign. Pour obtenir le complet des champs pris en charge, reportez-vous à la documentation [Utilisation d’Adobe Sign dans un formulaire](https://docs.adobe.com/content/help/en/experience-manager-65/forms/adaptive-forms-advanced-authoring/working-with-adobe-sign.html) adaptatif.
* Utilisez des sous-formulaires dans le XDP pour créer des panneaux dans les formulaires adaptatifs. Le service convertit chaque sous-formulaire en panneau de formulaire adaptatif pendant la conversion.
* Si possible, convertissez des tableaux complexes dans le XDP en tableaux simples.

### Avant d’ la conversion

* Créez des modèles de formulaire adaptatif. Les modèles permettent de définir une structure uniforme pour les formulaires de votre organisation ou de votre service.
* Spécifiez l’en-tête et le pied de page dans les modèles de formulaire adaptatif. Le service ignore l’en-tête et le pied de page des documents  sources et utilise l’en-tête et le pied de page spécifiés dans le modèle de formulaire adaptatif.
* Créez des  de formulaire adaptatif. Les  vous aident à donner une apparence uniforme aux formulaires de votre organisation ou de votre service.
* Configurez le modèle de données de formulaire pour enregistrer et récupérer une source de données. Créez et configurez des services de lecture et d’écriture pour le modèle de données de formulaire.
* Créez des fragments de formulaire adaptatif et configurez le service pour utiliser vos fragments de formulaire adaptatif.
* Préparez des modèles de processus courants pour les formulaires qui nécessitent l’automatisation des processus d’entreprise.
* Configuration d’Adobe Analytics, le cas échéant


## Modèles complexes connus

Le service de conversion automatisée AEM Forms utilise l’intelligence artificielle et des algorithmes d’apprentissage automatique pour comprendre la disposition et les champs du formulaire source. Chaque service d’apprentissage automatique tire sans cesse des enseignements des données sources et enregistre ainsi des résultats de plus en plus concluants. Tout comme les humains, ces services apprennent par l’expérience.

Le service de conversion automatisée de formulaires se base sur un large éventail de formulaires. Il identifie facilement les champs d’un formulaire source et génère des formulaires adaptatifs. Cependant, certains champs et styles des formulaires PDF, pourtant facilement visibles par l’œil humain, restent difficiles à comprendre pour le service. Le service peut affecter des types de champs ou des panneaux différents de ceux applicables à certains champs ou styles. Tous ces modèles de champ et de style sont répertoriés ci-dessous.

Le service commencerait à identifier et à attribuer à ces modèles des champs ou des panneaux adaptés tout en continuant à apprendre des données sources. Pour le moment, vous pouvez utiliser l’éditeur [de vérification et de correction](review-correct-ui-edited.md) pour résoudre ces problèmes. Avant de commencer à résoudre les problèmes ou de poursuivre votre lecture, familiarisez-vous avec les [composants de formulaires adaptatifs](https://helpx.adobe.com/fr/experience-manager/6-5/forms/using/introduction-forms-authoring.html).

### Modèles généraux {#general}

| Modèle | Exemple |
|--- |--- |
| **Modèle** <br> Le service ne convertit pas les formulaires PDF colorés en formulaires adaptatifs. <br><br>**Résolution **<br>Utilisez des formulaires PDF en noir et blanc ou en niveaux de gris. | ![Formulaire coloré](assets/best-practice-coloured-forms.png) |
| **Modèle** <br>Le service ne convertit pas les formulaires PDF remplis en formulaires adaptatifs. <br><br>**Résolution **<br>Utilisez des formulaires adaptatifs vides. | ![Formulaire rempli](assets/best-practice-filled-forms.png) |
| **Modèle** <br>Le service peut ne pas reconnaître le texte et les champs denses. <br><br>**Résolution **<br>Laissez davantage d’espace entre le texte et les champs denses avant de débuter la conversion. |  |
| **Modèle** <br>Le service ne prend pas en charge les formulaires numérisés. <br><br>**Résolution **<br>N’utilisez pas de formulaires numérisés. | ![Formulaire numérisé](assets/scanned-forms.png) |
| **Modèle** <br>Le service n’extrait pas d’images et de texte figurant dans les images. <br><br>**Résolution **<br>Ajoutez manuellement des images ou du texte aux formulaires convertis. | ![Formulaire avec image contenant du texte](assets/best-practice-image-with-text.png) |
| **Modèle** <br>Les tableaux dont les bordures sont en pointillés ou ne sont pas clairement définies ne sont pas convertis. <br><br>**Résolution **<br>Utilisez des tableaux dont les bordures sont clairement définies. pris en charge. | ![Formulaire avec tableau non clair](assets/best-practice-table-dotted-non-clear.png) |
| **Modèle** <br> Le formulaire adaptatif ne prend pas en charge le texte vertical en dehors de la case. Ainsi, le service ne convertit pas le texte vertical en texte de formulaires adaptatifs correspondant. <br><br>**Résolution **<br>Utilisez l’éditeur de formulaire adaptatif pour ajouter du texte vertical, si nécessaire. | ![Formulaire avec tableau non clair](assets/vertical-text.png) |



### Groupe de choix  {#choice-group}

| Modèle | Résolution |
|--- |--- |
| **Modèle** <br> Les options de groupe de choix sous d’autres formes que des cases ou des cercles ne sont pas converties en composants de formulaires adaptatifs correspondants. <br><br>**Résolution **<br>Donnez aux options de choix la forme de cases ou de cercles ou utilisez l’éditeur de vérification et de correction pour identifier les formes. | ![Champs de choix ](assets/best-practice-choice-group-options.png) |

### Champs de formulaire {#form-fields}

| Modèle | Résolution |
|--- |--- |
| **Modèle** <br> Le service n’identifie pas les champs dont les bordures ne sont pas clairement définies. <br><br>**Résolution **<br>Utilisez l’éditeur de vérification et de correction pour identifier ces champs. | ![champs dont les bordures ne sont pas clairement définies](assets/best-practice-fields-without-clear-borders.png) |
| **Modèle** <br> Le service peut ne pas identifier certains champs de formulaire de groupe de choix avec des légendes en bas ou à droite d’un formulaire. <br><br>**Résolution **<br>Utilisez l’éditeur de vérification et de correction pour identifier ces champs | ![Champs de choix](assets/best-practice-caption-bottom-right.png) |
| **Modèle** <br> Le service fusionne ou attribue un type incorrect à certains champs de formulaire placés très près les uns des autres ou dont les bordures ne sont pas clairement définies. <br><br>**Résolution **<br>Utilisez l’éditeur de vérification et de correction pour identifier ces champs. | ![Champs de choix](assets/best-practice-placed-very-near.png) |
| **Modèle** <br> Le service peut ne pas reconnaître les champs dont les légendes sont éloignées ou avec une ligne pointillée entre la légende et le champ d’entrée. <br><br>**Résolution **<br>Utilisez des champs de formulaire avec des bordures clairement définies ou utilisez l’éditeur de vérification et de correction pour corriger ces problèmes. | ![Champs éloignés ou ligne pointillée entre le champ et la légende](assets/best-practice-far-away-captions-or-a-dotted-line.png) |

### Listes {#lists}

| Modèle | Résolution |
|--- |--- |
| **Modèle** <br>Les listes contenant des champs de formulaire sont fusionnées ou ne sont pas converties en composants de formulaires adaptatifs correspondants <br><br>**Résolution **<br>Utilisez des champs de formulaire avec des bordures clairement définies ou utilisez l’éditeur de vérification et de correction pour corriger ces problèmes. | ![listes contenant des groupes de choix](assets/best-practice-lists-containing-form-fields.png) |
| **Modèle** <br>Le service peut ne pas identifier quelques listes imbriquées <br><br>**Résolution **<br>Utilisez l’éditeur de vérification et de correction pour résoudre ces problèmes. | ![listes contenant des groupes de choix](assets/best-practice-nested-lists.png) |
| **Modèle** <br> Le service fusionne certaines listes contenant des groupes de choix <br><br>**Résolution **<br>Utilisez l’éditeur de vérification et de correction pour résoudre ces problèmes. | ![listes contenant des groupes de choix](assets/best-practice-check-box-in-table-cells.png) |

<!--
Comment Type: draft

<h3>Choice groups</h3>
-->

<!--
Comment Type: draft

<ul>
<li>Lists with form fields, nested lists, and nested choice groups are not supported.</li>
<li>Form fields with captions at bottom or right are not supported.</li>
<li>Form fields without borders are not supported.</li>
<li>Hidden form fields are not supported.</li>
<li>Button in PDF forms are not converted to adaptive form buttons.<br /> </li>
<li>Tables with clear explicit boundaries and borders are supported.</li>
<li>Fields with far away captions are not supported.<br /> </li>
<li>Choice groups with only box or circle shaped selectors are supported. </li>
</ul>
-->
