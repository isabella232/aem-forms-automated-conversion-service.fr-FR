---
title: 'Dépannage du service de conversion automatisée des formulaires '
seo-title: 'Résolution des problèmes du service de conversion automatisée des formulaires (AFCS) '
description: 'Problèmes courants de l''AFCS et leurs solutions '
seo-description: Problèmes courants de l'AFCS et leurs solutions
contentOwner: khsingh
topic-tags: forms
translation-type: tm+mt
source-git-commit: 638d2adec39a4ecba335ae7bdebebd8bf9ab2274

---


# Dépannage du service de conversion automatisée des formulaires


L’article fournit des informations sur les problèmes d’installation, de configuration et d’administration qui peuvent survenir dans un de production  service de conversion automatisée de formulaires. Le  fournit également des étapes de dépannage de base et une explication des messages d’erreur courants.

## Erreurs courantes {#commonerrors}

| Erreur | Exemple |
|--- |--- |
| **Message** d’erreur <br> L’en-tête  n’est pas disponible. <br><br>**Raison **<br>: un administrateur a créé plusieurs configurations IMS ou la configuration IMS n’est pas en mesure d’accéder au service AFCS sur Adobe Cloud.<br><br>**Résolution**<br> S&#39;il existe plusieurs configurations, supprimez toutes les configurations et [créez une nouvelle configuration](configure-service.md#obtainpubliccertificates). <br> S’il existe une configuration unique, **[!UICONTROL Health Check]** vérifiez la connectivité [](configure-service.md#createintegrationoption). | ![L&#39;en-tête  du n&#39;est pas disponible](assets/invalid-ims-configuration.png) |
| **Message** d’erreur <br> Impossible de se connecter au service.  <br><br>**Raison **<br>d’une URL de service incorrecte ou d’aucune URL de service mentionnée dans les services cloud Service de conversion de formulaires automatisés.<br><br>**Résolution**<br> URL [de](configure-service.md#configure-the-cloud-service) service correct dans les services Cloud du service de conversion automatisée des formulaires. | ![Impossible de se connecter au service.](assets/wrong-endpoint-configured.png) |
| **Message** d’erreur <br> Impossible de se connecter au service.  <br><br>**Raison **<br>d’une URL de service incorrecte ou d’aucune URL de service mentionnée dans les services cloud Service de conversion de formulaires automatisés.<br><br>**Résolution**<br> URL [de](configure-service.md#configure-the-cloud-service) service correct dans les services Cloud du service de conversion automatisée des formulaires. | ![Impossible de se connecter au service.](assets/wrong-endpoint-configured.png) |