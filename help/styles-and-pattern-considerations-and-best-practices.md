---
title: 'Meilleures pratiques et considérations '
seo-title: 'Meilleures pratiques et considérations '
description: Meilleures pratiques et considérations relatives au service de conversion automatisée des formulaires
seo-description: Liste des styles et modèles dans les formulaires PDF source que le service de conversion automatisée des formulaires trouve difficile à identifier
uuid: e24773a2-be14-4184-a168-48aa976d459a
topic-tags: introduction
discoiquuid: 79f2026e-73a5-4bd1-b041-d1399b4ad23e
translation-type: tm+mt
source-git-commit: 0f413a8bc0bb444b6faaddaf32f84f36e38438a5

---


# Meilleures pratiques et modèles complexes connus {#Best-practices-and-considerations2}

Ce document fournit des directives et des recommandations dont peuvent bénéficier l’administrateur, les auteurs et les développeurs de formulaires lorsque vous utilisez le service de conversion automatisée des formulaires. Il aborde les meilleures pratiques, depuis la préparation des formulaires source jusqu’à la correction de modèles complexes qui nécessitent des efforts supplémentaires pour la conversion automatisée. Ces meilleures pratiques contribuent collectivement aux performances globales et à la sortie du service de conversion automatisée des formulaires.

## Meilleures pratiques

Le service de conversion convertit les formulaires PDF disponibles sur votre instance AEM Forms en formulaires adaptatifs. Vous pouvez télécharger tous les formulaires PDF en une seule fois ou par étapes, selon les besoins. Avant de télécharger les formulaires, tenez compte des points suivants :

* Conservez le nombre de formulaires dans un dossier inférieur à 15 et le nombre total de pages dans un dossier inférieur à 50.
* Conservez la taille du dossier inférieure à 10 Mo. Ne conservez pas les formulaires dans un sous-dossier.
* Conserver le nombre de pages dans un formulaire inférieur à 15.
* Ne transférez pas les formulaires protégés. Le service ne convertit pas les formulaires protégés par mot de passe et sécurisés.
* Ne transférez pas les portfolios [PDF](https://helpx.adobe.com/acrobat/using/overview-pdf-portfolios.html). Le service ne convertit pas un portfolio PDF en formulaires adaptatifs.
* Ne transférez pas les formulaires numérisés, colorés, non anglophones et remplis. Ces formulaires ne sont pas pris en charge.
* Ne transférez pas les formulaires source avec des espaces dans le nom de fichier. Supprimez l’espace du nom du fichier avant de télécharger les formulaires.
* Utilisez les modèles de formulaire adaptatif pour spécifier l’en-tête et le pied de page pour le formulaire adaptatif de sortie. Le service ignore l’en-tête et le pied de page des documents PDF source et utilise l’en-tête et le pied de page spécifiés dans le modèle de formulaire adaptatif.

## Connaître les modèles complexes

Le service de conversion automatisée AEM Forms utilise l’intelligence artificielle et des algorithmes d’apprentissage automatique pour comprendre la disposition et les champs du formulaire source. Chaque service d’apprentissage automatique apprend en permanence des données source et produit une sortie améliorée à chaque exécution. Ces services apprennent de l&#39;expérience comme les humains.

Le service de conversion automatisée des formulaires est formé sur un grand ensemble de formulaires. Il identifie facilement les champs d’un formulaire source et génère des formulaires adaptatifs. Cependant, certains champs et styles des formulaires PDF sont facilement visibles à l’oeil humain mais difficiles à comprendre pour le service. Le service peut affecter des types de champs ou des panneaux différents de ceux applicables à certains champs ou styles. Tous ces modèles de champ et de style sont répertoriés ci-dessous.

Le service commencerait à identifier et à affecter des champs ou des panneaux corrects à ces modèles car il continuerait à apprendre des données source. Pour le moment, vous pouvez utiliser [l’éditeur Révision et Correct](review-correct-ui-edited.md) pour résoudre ces problèmes. Avant de commencer à résoudre les problèmes ou à lire davantage, familiarisez-vous avec les composants [de formulaire](https://helpx.adobe.com/experience-manager/6-5/forms/using/introduction-forms-authoring.html)adaptatif.

### Formats généraux {#general}

| Modèle | Résolution |
|--- |--- |
| **Le service de modèle** <br> ne convertit pas les formulaires PDF colorés en formulaires adaptatifs. <br><br>**Résolution **<br>Utiliser des formulaires PDF en noir et blanc ou en niveaux de gris. | ![Forme colorée](assets/best-practice-coloured-forms.png) |
| **Le** service de modèle <br>ne convertit pas les formulaires PDF remplis en formulaires adaptatifs. <br><br>**Résolution **:<br>utilisez des formulaires adaptatifs vides. | ![Formulaire rempli](assets/best-practice-filled-forms.png) |
| **Le** service de schémas <br>peut ne pas reconnaître le texte et les champs sous une forme dense. <br><br>**Résolution **<br>Augmentez la largeur entre le texte et les champs d’un formulaire dense avant de commencer la conversion. |  |
| **Le** service de modèles <br>ne prend pas en charge les formulaires numérisés. <br><br>**Résolution **N&#39;<br>utilisez pas les formulaires numérisés. | ![Formulaire numérisé](assets/scanned-forms.png) |
| **Le** service de modèles <br>n’extrait pas les images et le texte dans les images. <br><br>**Résolution **<br>Ajoutez manuellement des images ou du texte aux formulaires convertis. | ![Image avec formulaire texte](assets/best-practice-image-with-text.png) |
| **Les** tableaux de modèles <br>avec des bordures et des bordures en pointillés ou non clairs ne sont pas convertis. <br><br>**Résolution **Utilisez<br>des tableaux avec des limites et des bordures explicites claires. pris en charge. | ![Formulaire de tableau non clair](assets/best-practice-table-dotted-non-clear.png) |
| **Modèle** <br> Le formulaire adaptatif ne prend pas en charge le texte vertical prêt à l’emploi. Le service ne convertit donc pas le texte vertical en texte de formulaires adaptatifs correspondant. <br><br>**Résolution **<br>Utilisez l’éditeur de formulaire adaptatif pour ajouter du texte vertical, le cas échéant. | ![Formulaire de tableau non clair](assets/vertical-text.png) |



### Groupe de choix {#choice-group}

| Modèle | Résolution |
|--- |--- |
| **Les options de groupe Choix de modèle**<br> avec des formes autres que la zone ou le cercle ne sont pas converties en composants de formulaire adaptatif correspondants. <br><br>**Résolution **<br>Modifiez les formes d’options de choix pour les encadrer ou les entourer ou utilisez l’éditeur de révision et de correction pour identifier les formes. | ![Champs de choix ](assets/best-practice-choice-group-options.png) |

### Form fields {#form-fields}

| Modèle | Résolution |
|--- |--- |
| **Le service de modèles** <br> n’identifie pas les champs sans bordures claires. <br><br>**Résolution **<br>Utilisez l’éditeur Révision et Correct pour identifier ces champs. | ![champs avec des limites non claires](assets/best-practice-fields-without-clear-borders.png) |
| **Le service de modèles** <br> peut ne pas identifier certains champs de formulaire de groupe de choix avec des légendes en bas ou à droite d’un formulaire. <br><br>**Résolution **Utilisez l’éditeur Révision et Correct<br>pour identifier ces champs. | ![Champs de choix](assets/best-practice-caption-bottom-right.png) |
| **Le service de modèle** <br> fusionne ou affecte un type incorrect à certains champs de formulaire qui sont placés très près les uns des autres ou qui n’ont pas de bordures claires. <br><br>**Résolution **<br>Utilisez l’éditeur Révision et Correct pour identifier ces champs. | ![Champs de choix](assets/best-practice-placed-very-near.png) |
| **Le service de modèles** <br> peut ne pas reconnaître les champs avec des légendes lointaines ou une ligne pointillée entre la légende et le champ de saisie. <br><br>**Résolution **<br>Utilisez les champs de formulaires avec des limites claires ou utilisez l’éditeur Révision et Correction pour résoudre ces problèmes. | ![Loin des champs ou de la ligne pointillée entre les champs de légende](assets/best-practice-far-away-captions-or-a-dotted-line.png) |

### Listes {#lists}

| Modèle | Résolution |
|--- |--- |
| **Les** listes de modèles <br>contenant des champs de formulaire sont fusionnées ou ne sont pas converties en composants de formulaire adaptatif correspondants <br><br>**Résolution **<br>Utiliser des champs de formulaire avec des limites claires ou utiliser l’éditeur de révision et de correction pour résoudre ces problèmes. | ![listes contenant des groupes de choix](assets/best-practice-lists-containing-form-fields.png) |
| **Le** service de schémas <br>peut laisser quelques listes imbriquées non identifiées <br><br>**Resolution **<br>Use Review et Correct Editor pour résoudre ces problèmes. | ![listes contenant des groupes de choix](assets/best-practice-nested-lists.png) |
| **Le service de schémas**<br> fusionne certaines listes contenant des groupes de choix les unes avec les autres <br><br>**Résolution **<br>Utiliser la révision et l’éditeur Correct pour résoudre ces problèmes. | ![listes contenant des groupes de choix](assets/best-practice-check-box-in-table-cells.png) |

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
