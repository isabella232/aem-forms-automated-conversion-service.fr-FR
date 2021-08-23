---
title: 'Nouveautés Notes de mise à jour : service de conversion automatisée de formulaires'
description: En savoir plus sur les dernières fonctionnalités et le bogue corrigé pour le service de conversion automatisée de formulaires
exl-id: fccafbc9-28c1-4736-922c-24d675b25213
source-git-commit: 3bf065a754d8e8f97a660eb2ae39f37341bb4668
workflow-type: ht
source-wordcount: '431'
ht-degree: 100%

---

# Notes de mise à jour

Le service de conversion automatisée de formulaires est continuellement amélioré. Pour vous tenir au courant des dernières nouveautés, consultez régulièrement cette page. Cette page vous fournit les informations suivantes :

* Accès anticipé
* Dernières versions
* Nouvelles fonctionnalités
* Améliorations
* Correctifs
* Fonctionnalités obsolètes
* Instructions spéciales
* Changements prévus

## 29 juillet 2021 (AFC-2021.07.2) {#july-2021}

* Ajout de la possibilité de convertir en formulaires adaptatifs les formulaires PDF en français, allemand et espagnol.

## 24 juin 2021 (AFC-2021.06.2) {#june-2021}

### Améliorations {#june-2021-improvements}

Amélioration de la précision de la détection automatique des sections logiques dans les formulaires sources et de leur conversion en panneaux de formulaires adaptatifs correspondants.

## 3 mars 2021 (AFC-2021.02.2) {#mar-2021}

### Améliorations {#march-2021-improvements}

Améliorations apportées à l’organisation du contenu de formulaire dans des groupes de choix et des champs lors de la conversion d’un formulaire source en formulaire adaptatif.

## 2 février 2021 (AFC-2021.01.2) {#feb-2021}

### Améliorations {#feb-2021-improvements}

Améliorations apportées à l’organisation du contenu du formulaire dans les panneaux et à la génération de titres pour les panneaux lors de la conversion d’un formulaire source en formulaire adaptatif.

## 16 juillet 2020 (AFC-2020.07.2) {#jul-2020}

### Nouveautés {#whats-new-jul-2020-}

Ajout de la prise en charge de la conversion des formulaires PDF colorés en formulaires adaptatifs.

### Améliorations {#jul-2020-improvements}

Améliorations de la conversion automatisée des champs de texte, de formulaire et de groupe de choix vers des composants de formulaire adaptatif correspondants.


## 20 mars 2020 (AFC-2020.03.1) {#mar-2020}

### Accès anticipé {#early-access}

**Détection automatique de sections logiques dans un formulaire**

Par défaut, le service crée un panneau de niveau supérieur distinct pour chaque page d’un formulaire PDF. Vous pouvez désormais utiliser l’option **[!UICONTROL Auto-detect logical sections]** (Détection automatique de sections logiques) pour abandonner les panneaux au niveau de la page (panneaux basés sur le numéro de page) et créer uniquement des panneaux logiques. Il regroupe également les champs qui n’appartiennent à aucune section avec la section logique précédente et les champs d’une section logique répartis sur deux pages adjacentes en une seule section logique. Par exemple, si certains champs d’une section logique se trouvent à la fin de la première page et d’autres au début de la deuxième page, tous ces champs sont regroupés en une seule section logique.

### Améliorations {#mar-2020-improvements}

**Amélioration de la détection de listes**

Le service détecte désormais plus efficacement les listes à puces et numérotées.

### Instructions spéciales {#special-instructions}

**Installation du package connecteur du service de conversion automatisée de formulaires**

Le package connecteur 1.1.38 ou version ultérieure est nécessaire pour utiliser les dernières fonctionnalités et améliorations proposées dans la version AFC-2020.03.1. Vous pouvez télécharger le package connecteur depuis le [partage de package AEM](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq650/featurepack/AFCS-Connector-2020.03.1).

Si vous disposez déjà d’un environnement de service de conversion automatisée de formulaires opérationnel, installez les derniers Service Pack, module complémentaire AEM Forms et package connecteur dans cet ordre pour en utiliser les dernières fonctionnalités. Pour obtenir des instructions détaillées, consultez l’article [Configurer le service de conversion automatisée de formulaires](configure-service.md).
