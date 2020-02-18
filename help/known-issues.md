---
title: Problèmes connus
seo-title: Problèmes connus
description: problèmes connus et limites du service de conversion automatisée des formulaires
seo-description: Avant de commencer à utiliser le service de conversion automatisée des formulaires AEM Forms, découvrez les problèmes et les limites connus du service.
uuid: b1dc661b-ccd3-457f-acbb-4bd25db86e1e
topic-tags: introduction
discoiquuid: 9cd2363c-47a0-46e9-98cd-1fe088b9cd6e
translation-type: tm+mt
source-git-commit: 2fcceb45d9be4297fcd923f5a17c7b593294e855

---

# Problèmes et limites connus {#known-issues-limitations}

Avant de commencer à utiliser le service de conversion automatisée des formulaires AEM Forms, vérifiez les problèmes et restrictions connus suivants :

## Problèmes connus {#known-issues}

* Le dossier contenant des formulaires à convertir ne doit pas comporter plus de 15 formulaires et 50 pages au total. La taille du dossier source ne doit pas dépasser 10 Mo. Ne créez pas de sous-dossiers dans le dossier source.
* Certains objets de formulaire sont facilement visibles à l’oeil humain mais sont [difficiles à identifier pour le service](styles-and-pattern-considerations-and-best-practices.md). Utilisez l’éditeur [](review-correct-ui-edited.md) de révision et l’éditeurcorrect pour identifier et convertir ces objets de formulaire.
* Editeur de révision et de correction :

   * N’a pas d’action Annuler. Le bouton Enregistrer enregistre les modifications de manière permanente.
   * Ne prend pas en charge les panneaux répétables pour les formulaires XFA.
   * Si vous modifiez une liste d’un tableau à l’aide de l’éditeur Révision et Correction, la largeur des rangées ne s’ajuste pas automatiquement et le texte risque de déborder sur la rangée suivante du tableau.
   * La **[!UICONTROL Auto-detect multi-column layout from input forms]** fonctionnalité ne fonctionne pas avec l’éditeur de révision et de correction et les fragments de formulaire.

* Pour les formulaires XFA :
   * L’extraction de fragments d’un formulaire XFA n’est pas prise en charge.
   * Les scripts XFA ne sont pas pris en charge. Par exemple, les scripts permettant de générer automatiquement des valeurs pour un composant déroulant.
   * Le méta-modèle ne fonctionne pas pour le groupe de choix
   * Les options Groupes de choix avec un caractère unique ne sont pas identifiées
   * Lorsque le document source est un XFA dynamique (.XDP) et qu’il [définit le comportement des propriétés XFA dans un formulaire](https://helpx.adobe.com/experience-manager/6-5/forms/using/xfa-api-supported-in-adaptive-form.html#supportedxfaelementsandtheirmappinginadaptiveformsbr)adaptatif, la propriété presence du document source n’est pas respectée. Par exemple, un champ du document source est marqué comme masqué et un script rend le champ visible, puis le champ reste visible dans le formulaire adaptatif de sortie.

* Lorsque vous utilisez l’option **Utiliser AcroForm en entrée comme document d’enregistrement (DE) pour les formulaires** adaptatifs générés, tenez compte des points suivants :

<table>
    <tr>
        <td>La liaison et les données sont perdues pour les champs de texte composites. Un champ de texte composite comporte plusieurs zones de texte alignées l’une sur l’autre. Par exemple, dans un formulaire AcroForm, un numéro de carte de crédit est divisé en plusieurs zones de texte et chaque zone de texte a une liaison distincte. Lorsque l’AcroForm est converti en formulaire adaptatif, le formulaire adaptatif converti a une liaison unique pour toutes les zones de texte. Pour pallier ce problème, avant de convertir un formulaire AcroForm en formulaire adaptatif, modifiez le formulaire AcroForm afin qu’il utilise une zone de texte unique pour accepter les numéros de carte de crédit.</td>
        <td><img  src="assets/creditCard_Composite.png"/>                                                            </td>
    </tr>
    <tr>
        <td>La liaison et les données sont perdues pour les champs de date composites. Un champ de date composite est composé de trois champs différents. Par exemple, un champ de date de naissance dans un formulaire AcroForm est divisé en trois champs distincts. Le formulaire adaptatif fournit un composant de sélecteur de date prêt à l’emploi. Pour utiliser le composant de sélecteur de date du formulaire adaptatif tout en conservant la liaison de l’AcroForm, avant de convertir un AcroForm en formulaire adaptatif, modifiez l’AcroForm pour qu’il utilise un seul champ de date.</td>
        <td><img  src="assets/CompositeDateField.png"/></td>
    </tr>
    <tr>
        <td>Si la taille des cases à cocher est supérieure au texte qui les accompagne, elles ne sont pas détectées et la liaison dans AcroForm est perdue. Modifiez l’AcroForm pour que la taille des cases à cocher soit plus petite que le texte qui l’accompagne.</td>
        <td><img  src="assets/large-text-box.png"/><br/><img  src="assets/small-text-box.png"/></td>
    </tr>
    <tr>
        <td>Si les champs de saisie ne sont pas alignés sur le champ de texte correspondant, le champ de saisie n’est pas détecté.  </td>
        <td><img  src="assets/non-alingned-fields.png"/></td>
    </tr>
    <tr >
        <td>Le service convertit toutes les cases à cocher d’un AcroForm en groupes de choix distincts. Des groupes de choix distincts sont créés pour conserver les liaisons avec AcroForm. Ne fusionnez pas les groupes de choix dans le formulaire adaptatif. Cela entraînera une perte des liaisons. Si vous fusionnez les groupes de choix, convertissez de nouveau le formulaire pour récupérer les liaisons perdues. </td>
        <td></td>
    </tr>
    <tr >
        <td>Les limites de certains tableaux sont étendues hors de la page dans le document d’enregistrement généré automatiquement. </td>
        <td></td>
    </tr>
</table>

## Restrictions {#limitations}

* Les formulaires PDF avec une disposition dynamique complexe, les champs avec contour en pointillé, les champs remplis ou les champs colorés ne sont pas pris en charge.
* Les images et le texte à l’intérieur des images ne sont pas identifiés. Ajouter manuellement des images aux formulaires convertis.
* Les documents XDP d’illustration ne sont pas pris en charge.
* Les formulaires PDF de plus de 15 pages ne sont pas pris en charge.
* Les documents chiffrés, protégés par mot de passe et sécurisés ne sont pas convertis. Supprimez le chiffrement ou les mots de passe avant d’exécuter la conversion.
* Les tableaux complexes tels que les tableaux sans bordure, les tableaux imbriqués, les tableaux avec des rangées colorées et les tableaux avec des valeurs d’espace réservé ne sont pas pris en charge. Utilisez l’éditeur de formulaires adaptatifs pour ajouter ou modifier des tableaux complexes après la conversion. Seuls les tableaux simples, avec des champs vides, des en-têtes appropriés et des limites claires sont pris en charge.
* Le service convertit uniquement les formulaires en anglais en formulaires adaptatifs. Vous pouvez traduire des formulaires adaptatifs convertis dans une autre langue à l’aide du processus [de traduction](https://helpx.adobe.com/experience-manager/6-5/forms/using/using-aem-translation-workflow-to-localize-adaptive-forms.html)AEM.
* AEM Forms 6.4 ne prend pas en charge la détection automatique de la disposition à plusieurs colonnes des formulaires d’entrée.

