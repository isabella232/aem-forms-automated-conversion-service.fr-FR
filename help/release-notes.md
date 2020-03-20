---
title: Nouveautés? Notes de mise à jour - Service de conversion de formulaires automatisés
description: 'Découvrez les dernières fonctionnalités et le bogue corrigé pour le service de conversion automatisée des formulaires. '
translation-type: tm+mt
source-git-commit: 01dfd20951314017d47713bfb1a2a5f2d563f434

---


# Service de conversion de formulaires automatisés : Notes de mise à jour

Le service de conversion automatisée des formulaires reçoit régulièrement des améliorations. Pour être au courant des derniers développements, visitez cette page régulièrement. Cette page contient des informations sur :

* Dernières versions
* Nouvelles fonctionnalités
* Correctifs
* Fonctionnalité obsolète
* Instructions spéciales
* Plans futurs pour les changements

Cette page est mise à jour mensuellement, alors revisitez-la régulièrement.

## 20 mars 2020 (AFC-2020.03.1)

### Nouveautés

**Détecter automatiquement les sections logiques d’un formulaire**

Par défaut, le service crée un panneau de niveau supérieur distinct pour chaque page d’un formulaire PDF d’entrée. Vous pouvez désormais sélectionner l’ **[!UICONTROL Auto-detect logical sections]** option permettant de supprimer la notion de création d’un panneau supérieur distinct pour chaque page PDF et de détecter automatiquement les sections logiques. Les clubs de service associaient les champs d’un formulaire à une section logique. Par exemple, tous les champs liés à l’adresse de facturation sont regroupés en une section et tous les champs liés à l’adresse d’expédition sont regroupés en une autre section. Le service crée également un panneau de niveau supérieur distinct pour chaque section logique détectée automatiquement.

### Améliorations

**Améliorations de la détection des**

Le service est désormais plus efficace pour détecter les  à puces et à puces numérotées. Il peut désormais facilement détecter les  à plusieurs niveaux.

### Instructions spéciales

**Installation du package du connecteur du service de conversion de formulaires automatisés**

Vous avez besoin du module connecteur version 1.1.38 ou ultérieure pour utiliser les dernières fonctionnalités et améliorations fournies dans la version AFC-2020.03.1. Vous pouvez télécharger le module Connector à partir du partage [de package](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq650/servicepack/fd/AEM-Forms-6.5.4.0-WIN)AEM.

Si vous disposez déjà d’un de service de conversion automatisée des formulaires en cours d’exécution, pour utiliser les dernières fonctionnalités du service de conversion, installez le dernier Service Pack, le dernier module complémentaire AEM Forms et le dernier module connecteur dans l’ordre mentionné. Pour obtenir des instructions détaillées, reportez-vous à l’article [Configuration du service](configure-service.md) de conversion automatisée des formulaires.
