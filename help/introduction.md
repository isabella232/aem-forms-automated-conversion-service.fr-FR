---
title: Présentation
description: 'Accélérer la conversion des formulaires imprimés en formulaires adaptatifs '
translation-type: tm+mt
source-git-commit: 53b88de185ed1b6669ecfc3c7c6649d5627741e9
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 78%

---


# Présentation {#introduction-to-automated-forms-conversion-service}

Le service de conversion automatisée de formulaires permet d’accélérer la numérisation et la modernisation de l’expérience de capture de données grâce à la conversion automatisée de formulaires PDF en formulaires adaptatifs. Ce service, optimisé par Adobe Sensei, convertit automatiquement vos formulaires PDF en formulaires adaptatifs réactifs, basés sur HTML5 et compatibles avec divers appareils. Tout en tirant parti des investissements existants dans les formulaires PDF et XFA, le service applique également les validations, le style et la mise en page appropriés aux champs de formulaires adaptatifs lors de la conversion. Le service aide à :

* réduire les efforts manuels requis pour la conversion de formulaires imprimés en formulaires adaptatifs ;
* appliquer des modèles et des validations adaptés lors de la conversion ;
* générer un document d’enregistrement au cours de la conversion ;
* Regrouper les champs courants dans des fragments de formulaire réutilisables
* activer Adobe Analytics pendant la conversion.

![C’est simple. Vous nous fournissez les formulaires sources et nous laissez tout. Nous vous fournissons de superbes formulaires adaptatifs. Vous pouvez toujours bricoler avec la sortie à votre satisfaction. ](assets/pdf-to-adaptive-form-gitx50.gif)

## Intégration {#onboarding}

Le service est disponible gratuitement pour AEM 6.4 Forms et AEM 6.5 Forms On-Premise clients et pour les clients d&#39;entreprise de services gérés par Adobe. Vous pouvez contacter l’équipe de ventes d’Adobe ou votre représentant Adobe pour demander l’accès au service. Le service est également disponible gratuitement et préactivé pour AEM Forms en tant que client Cloud Service.

Adobe autorise l’accès de votre entreprise et fournit les privilèges requis à la personne désignée comme administrateur au sein de votre entreprise. L’administrateur peut autoriser les développeurs (utilisateurs) AEM Forms de votre entreprise à se connecter au service. Pour en savoir plus, consultez la page [Configurer le service de conversion automatisée de formulaires](configure-service.md).

## PDF forms et langues pris en charge {#supported-languages-and-pdf-forms}

Le service prend en charge les formulaires PDF non interactifs, les formulaires créés avec Adobe Acrobat (AcroForms) et les formulaires basés sur XFA créés à l’aide d’AEM Forms ou d’Adobe LiveCycle.

Le service prend également en charge les PDF forms activés pour Adobe Sign. Si le formulaire PDF source contient des balises de texte Adobe Sign, le service conserve toutes les informations liées à Adobe Sign pendant la conversion et associe les informations du signataire présentes dans le PDF source aux champs de formulaire adaptatif correspondants. Cette fonction est disponible uniquement pour AcroForms.

Le service peut uniquement convertir les formulaires en anglais en formulaires adaptatifs. Vous pouvez traduire des formulaires adaptatifs générés dans une autre langue à l’aide du [Processus de traduction AEM](https://helpx.adobe.com/fr/experience-manager/6-5/forms/using/using-aem-translation-workflow-to-localize-adaptive-forms.html).

## Processus de conversion  {#conversion-workflow}

Le service de conversion automatisée de formulaires s’exécute sur Adobe Cloud. Connectez votre instance AEM au service, téléchargez des formulaires sur votre instance AEM et lancez la conversion. Le processus de conversion est détaillé ci-dessous :

![Processus](assets/conversion-workflow.png)

### 1. Configurer l’environnement {#set-up-the-environment}

Le service de conversion automatisée de formulaires s’exécute sur Adobe Cloud. [Configurez le compte Adobe I/O de votre entreprise et connectez votre instance AEM locale](configure-service.md) au service de conversion exécuté sur Adobe Cloud.

### 2. Convertir les formulaires PDF en formulaires adaptatifs {#use-the-conversion-service}

Une fois votre environnement AEM Forms configuré, pour convertir vos formulaires PDF en formulaires adaptatifs, [téléchargez des formulaires PDF](convert-existing-forms-to-adaptive-forms.md) sur votre instance AEM et [démarrez la conversion](convert-existing-forms-to-adaptive-forms.md#run-the-conversion). Avant de télécharger les formulaires, tenez compte des éléments suivants :

* Ne téléchargez pas de formulaires sécurisés. Le service ne convertit pas les formulaires protégés par mot de passe et chiffrés.
* Ne téléchargez pas de formulaires remplis, numérisés, en couleurs et dans une langue autre que l’anglais. Ces types de formulaires ne sont pas pris en charge.
* Ne téléchargez pas de formulaires PDF dont le nom comporte des espaces.
* Ne téléchargez pas de [portfolios PDF](https://helpx.adobe.com/fr/acrobat/using/overview-pdf-portfolios.html). Le service ne convertit pas un portfolio PDF en formulaire adaptatif.
* Apportez les modifications suggérées dans l’article [Bonnes pratiques et remarques](styles-and-pattern-considerations-and-best-practices.md) aux formulaires PDF.
* Pour éviter les pièges, reportez-vous à l’article [Problèmes connus](known-issues.md).

### 3. Vérifier les formulaires convertis {#review-converted-forms}

Les formulaires du monde réel peuvent présenter des exigences complexes de capture de données en termes de disposition des champs, de nommage ou de suggestions implicites qui peuvent ne pas être capturées avec précision par la logique de détection basée sur IA/ML. Une fois la conversion automatisée terminée, vous pouvez utiliser l’[éditeur de vérification et de correction](review-correct-ui-edited.md) pour vérifier le formulaire converti et apporter les modifications nécessaires afin d’obtenir le résultat souhaité. Après avoir apporté les modifications requises, renvoyez le formulaire pour conversion.

Le temps nécessaire à la conversion automatisée dépend de divers facteurs tels que la taille du formulaire d’entrée, la complexité du formulaire, le prêt sur la file d’attente de traitement du service. L’utilisateur est régulièrement informé de la progression via un indicateur d’état sur le dossier/fichier. Une fois la conversion terminée, une notification est également envoyée par courrier électronique à l’adresse configurée.
