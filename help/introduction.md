---
title: Introduction
description: 'Accélérer la conversion des formulaires d’impression en formulaires adaptatifs '
translation-type: tm+mt
source-git-commit: ceff5cb56aa9896a28004628c5e26c262b7918bd

---


# Présentation {#introduction-to-automated-forms-conversion-service}

Le service de conversion automatisée des formulaires permet d’accélérer la numérisation et la modernisation de l’expérience de capture de données grâce à la conversion automatisée des formulaires PDF en formulaires adaptatifs. Ce service, proposé par Adobe Sensei, convertit automatiquement vos formulaires PDF en formulaires adaptatifs compatibles avec les périphériques, réactifs et basés sur HTML5. Tout en exploitant les investissements existants dans les formulaires PDF et XFA, le service applique également les validations, le style et la mise en page appropriés aux champs de formulaire adaptatif pendant la conversion. Le service permet :

* Enregistrement de l’effort manuel requis pour convertir des formulaires d’impression en formulaires adaptatifs
* Applique des modèles et des validations appropriées lors de la conversion
* Générer un  d’enregistrement pendant la conversion
* Regroupez les champs les plus courants en fragments de formulaire réutilisables.
* Active Adobe Analytics pendant la conversion

![C&#39;est simple. Vous nous fournissez simplement les formulaires sources et nous laissez tout. Nous vous fournirons de superbes formulaires adaptatifs. Bien sûr, vous bricolerez avec le résultat à votre satisfaction. ](assets/pdf-to-adaptive-form-gitx50.gif)

## Intégration {#onboarding}

Ce service est disponible gratuitement pour les clients de longue durée d’AEM Forms 6.4 et d’AEM Forms 6.5 sur site et les clients d’entreprise du service géré Adobe. Vous pouvez contacter l’équipe commerciale d’Adobe ou votre représentant Adobe pour demander l’accès au service.

Adobe permet d’accéder à votre organisation et de fournir les privilèges requis à la personne désignée comme administrateur dans votre organisation. L’administrateur peut accorder l’accès aux développeurs (utilisateurs) d’AEM Forms de votre organisation pour la connexion au service. Voir [Configuration du service](configure-service.md) de conversion automatisée des formulaires pour plus d’informations.

## Formulaires et langues PDF pris en charge {#supported-languages-and-pdf-forms}

Le service prend en charge les formulaires PDF non interactifs, les formulaires créés avec Adobe Acrobat, appelés AcroForms, et les formulaires XFA créés à l’aide d’AEM Forms ou d’Adobe LiveCycle.

Le service peut convertir uniquement des formulaires en anglais en formulaires adaptatifs. Vous pouvez traduire les formulaires adaptatifs générés dans une autre langue à l’aide du processus [de traduction](https://helpx.adobe.com/experience-manager/6-5/forms/using/using-aem-translation-workflow-to-localize-adaptive-forms.html)AEM.

## Flux de conversion {#conversion-workflow}

Le service de conversion automatisée des formulaires s’exécute sur Adobe Cloud. Vous connectez votre instance AEM au service, téléchargez des formulaires vers votre instance AEM et la conversion. Le processus de conversion complet se présente comme suit :

![Processus](assets/conversion-workflow.png)

### 1. Configuration du  {#set-up-the-environment}

Le service de conversion automatisée des formulaires s’exécute sur Adobe Cloud. [Configurez le compte d’E/S Adobe de votre organisation et connectez votre instance](configure-service.md) AEM locale au service de conversion s’exécutant sur Adobe Cloud.

### 2. Conversion de formulaires PDF en formulaires adaptatifs {#use-the-conversion-service}

Une fois votre AEM Forms  configuré, pour convertir vos formulaires PDF en formulaires adaptatifs, [téléchargez des formulaires](convert-existing-forms-to-adaptive-forms.md) PDF vers votre instance AEM et [la conversion](convert-existing-forms-to-adaptive-forms.md#run-the-conversion). Avant de télécharger les formulaires, tenez compte des éléments suivants :

* Ne transférez pas les formulaires sécurisés. Le service ne convertit pas les formulaires chiffrés et protégés par mot de passe.
* Ne téléchargez pas de formulaires remplis, numérisés, en couleurs et dans une langue autre que l’anglais. Ces types de formulaires ne sont pas pris en charge.
* Ne transférez pas les formulaires PDF avec des espaces dans le nom de fichier.
* Do not upload [PDF Portfolios](https://helpx.adobe.com/acrobat/using/overview-pdf-portfolios.html). Le service ne convertit pas les portfolios PDF en formulaires adaptatifs.
* Effectuez les modifications suggérées dans les formulaires PDF décrites dans l’article [Meilleures pratiques et considérations](styles-and-pattern-considerations-and-best-practices.md) .
* Lisez l’article Problèmes [](known-issues.md) connus pour éviter les pièges.

### 3. Révision des formulaires convertis {#review-converted-forms}

Les formulaires du monde réel peuvent présenter des exigences complexes de capture de données en termes de disposition des champs, d’attribution de noms ou de suggestions implicites qui peuvent ne pas être capturées avec précision par la logique de détection basée sur IA/ML. Une fois la conversion automatisée terminée, vous pouvez utiliser l’éditeur [de](review-correct-ui-edited.md) révision et de correction pour examiner le formulaire converti et effectuer les mises à jour nécessaires et générer une sortie améliorée plus proche de l’expérience souhaitée. Après avoir apporté les modifications requises, envoyez de nouveau le formulaire pour la conversion.

Le temps nécessaire à la conversion automatisée dépend de divers facteurs, tels que la taille du formulaire d’entrée, la complexité du formulaire, le prêt sur la file d’attente de traitement du service. L’utilisateur est régulièrement informé de la progression par l’intermédiaire de l’indicateur d’état sur le dossier/fichier. Une fois la conversion terminée, une notification par courrier électronique est également envoyée à l’adresse électronique configurée.
