---
title: Nouveautés? Notes de mise à jour - Service de conversion de formulaires automatisés
description: 'Découvrez les dernières fonctionnalités et le bogue corrigé pour le service de conversion automatisée des formulaires. '
translation-type: tm+mt
source-git-commit: 6d658dbb181c09e42073e328e0232e40d4fb6b58

---


# Service de conversion de formulaires automatisés : Notes de mise à jour

Le service de conversion automatisée des formulaires reçoit régulièrement des améliorations. Pour être au courant des derniers développements, visitez cette page régulièrement. Cette page contient des informations sur :

* Dernières versions
* Nouvelles fonctionnalités
* Correctifs
* Fonctionnalité obsolète
* Instructions spéciales
* Plans futurs pour les changements

## 20 mars 2020 (AFC-2020.03.1)

### Nouveautés

**Détecter automatiquement les sections logiques d’un formulaire**

Par défaut, le service crée un panneau de niveau supérieur distinct pour chaque page d’un formulaire PDF. Désormais, vous pouvez utiliser l’ **[!UICONTROL Auto-detect logical sections]** option pour déposer les panneaux de niveau page (panneaux basés sur le numéro de page) et créer uniquement des panneaux logiques.  Il regroupe également les champs qui n’appartiennent à aucune section avec une section logique prédéfinie. Il regroupe également les champs d’une section logique répartis sur deux pages adjacentes en une seule section logique. Par exemple, si certains champs d’une section logique se trouvent à la fin de la page 1 et que d’autres se trouvent au début de la page 2, tous ces champs sont regroupés en une seule section logique.

### Améliorations

**Améliorations de la détection des**

Le service est désormais plus efficace pour détecter les  à puces et à puces numérotées. Il peut désormais facilement détecter les  à plusieurs niveaux.

### Instructions spéciales

**Installation du package du connecteur du service de conversion de formulaires automatisés**

Vous avez besoin du module connecteur version 1.1.38 ou ultérieure pour utiliser les dernières fonctionnalités et améliorations fournies dans la version AFC-2020.03.1. Vous pouvez télécharger le module Connector à partir du partage [de package](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq650/servicepack/fd/AEM-Forms-6.5.4.0-WIN)AEM.

Si vous disposez déjà d’un de service de conversion automatisée des formulaires en cours d’exécution, pour utiliser les dernières fonctionnalités du service de conversion, installez le dernier Service Pack, le dernier module complémentaire AEM Forms et le dernier module connecteur dans l’ordre mentionné. Pour obtenir des instructions détaillées, reportez-vous à l’article [Configuration du service](configure-service.md) de conversion automatisée des formulaires.
