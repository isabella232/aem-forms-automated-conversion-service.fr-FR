---
title: Nouveautés? Notes de mise à jour - Service de conversion de formulaires automatisés
description: 'Découvrez les dernières fonctionnalités et le bogue corrigé pour le service de conversion automatisée des formulaires. '
translation-type: tm+mt
source-git-commit: dc17dfcb331df6144b8a7ce3c9c9d840b1182a95

---


# Service de conversion de formulaires automatisés : Notes de mise à jour

Le service de conversion automatisée des formulaires reçoit régulièrement des améliorations. Pour être au courant des derniers développements, visitez cette page régulièrement. Cette page contient des informations sur :

* Accès anticipé
* Dernières versions
* Nouvelles fonctionnalités
* améliorations
* Correctifs
* Fonctionnalité obsolète
* Instructions spéciales
* Plans futurs pour les changements

## 20 mars 2020 (AFC-2020.03.1)

### Accès anticipé

**Détecter automatiquement les sections logiques d’un formulaire**

La version AFC-2020.03.1 fournit un accès précoce à la **[!UICONTROL Auto-detect logical sections]** fonctionnalité.

Par défaut, le service crée un panneau de niveau supérieur distinct pour chaque page d’un formulaire PDF. Désormais, vous pouvez utiliser l’ **[!UICONTROL Auto-detect logical sections]** option pour déposer les panneaux de niveau page (panneaux basés sur le numéro de page) et créer uniquement des panneaux logiques.  Il regroupe également les champs qui n’appartiennent à aucune section avec des sections logiques prédéfinies et les champs d’une section logique répartis sur deux pages adjacentes en une seule section logique. Par exemple, si certains champs d’une section logique se trouvent à la fin de la page 1 et que d’autres se trouvent au début de la page 2, tous ces champs sont regroupés en une seule section logique.

Vous avez besoin du connecteur package 1.1.38 ou version ultérieure pour utiliser la **[!UICONTROL Auto-detect logical sections]** fonctionnalité. You can download the connector package from [AEM Package Share](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq650/featurepack/AFCS-Connector-2020.03.1).

### Améliorations

**Améliorations de la détection des**

Le service est désormais plus efficace pour détecter les  à puces et à puces numérotées.