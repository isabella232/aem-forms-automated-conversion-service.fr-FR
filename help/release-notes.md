---
title: Nouveautés? Notes de mise à jour - Service de conversion de formulaires automatisés
description: 'Découvrez les dernières fonctionnalités et le bogue corrigé pour le service de conversion automatisée des formulaires. '
translation-type: tm+mt
source-git-commit: c0ca850a0a1e82e34364766601011d6367b218ac

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

Par défaut, le service crée un panneau de niveau supérieur distinct pour chaque page d’un formulaire PDF. Désormais, vous pouvez utiliser l’ **[!UICONTROL Auto-detect logical sections]** option pour déposer les panneaux de niveau page (panneaux basés sur le numéro de page) et créer uniquement des panneaux logiques. Il regroupe également les champs qui n’appartiennent à aucune section avec les sections logiques précédentes et les champs d’une section logique répartis sur deux pages adjacentes en une seule section logique. Par exemple, si certains champs d’une section logique se trouvent à la fin de la page 1 et que d’autres se trouvent au début de la page 2, tous ces champs sont regroupés en une seule section logique.

### Améliorations

**Améliorations de la détection des**

Le service est désormais plus efficace pour détecter les  à puces et à puces numérotées.

### Instructions spéciales

**Installation du package du connecteur du service de conversion de formulaires automatisés**

Vous avez besoin du module connecteur version 1.1.38 ou ultérieure pour utiliser les dernières fonctionnalités et améliorations fournies dans la version AFC-2020.03.1. Vous pouvez télécharger le module Connector à partir du partage [de package](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq650/featurepack/AFCS-Connector-2020.03.1)AEM.

Si vous disposez déjà d’un de service de conversion automatisée des formulaires en cours d’exécution, pour utiliser les dernières fonctionnalités du service de conversion, installez le dernier Service Pack, le dernier module complémentaire AEM Forms et le dernier module connecteur dans l’ordre mentionné. Pour obtenir des instructions détaillées, reportez-vous à l’article [Configuration du service](configure-service.md) de conversion automatisée des formulaires.