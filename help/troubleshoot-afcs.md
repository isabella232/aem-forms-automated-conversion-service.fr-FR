---
title: 'Dépannage du service de conversion automatisée des formulaires '
seo-title: 'Résolution des problèmes du service de conversion automatisée des formulaires (AFCS) '
description: 'Problèmes courants de l''AFCS et leurs solutions '
seo-description: Problèmes courants de l'AFCS et leurs solutions
contentOwner: khsingh
topic-tags: forms
translation-type: tm+mt
source-git-commit: 4b9f3f4fe3b3901cb99c9374ff40e8f49855237f

---


# Dépannage du service de conversion automatisée des formulaires


L’article fournit des informations sur les problèmes d’installation, de configuration et d’administration qui peuvent survenir dans un de production  service de conversion automatisée de formulaires. Le  fournit également des étapes de dépannage de base et une explication des messages d’erreur courants.

## Erreurs courantes {#commonerrors}

| Erreur | Exemple |
|--- |--- |
| **Message** d’erreur <br> L’en-tête  n’est pas disponible. <br><br>**Raison **<br>: un administrateur a créé plusieurs configurations IMS ou la configuration IMS n’est pas en mesure d’accéder au service AFCS sur Adobe Cloud.<br><br>**Résolution**<br> S&#39;il existe plusieurs configurations, supprimez toutes les configurations et [créez une nouvelle configuration](configure-service.md#obtainpubliccertificates). <br> S’il existe une configuration unique, **[!UICONTROL Health Check]** vérifiez la connectivité [](configure-service.md#createintegrationoption). | ![L&#39;en-tête  du n&#39;est pas disponible](assets/invalid-ims-configuration.png) |
| **Message** d’erreur <br> Impossible de se connecter au service.  <br><br>**Raison **<br>d’une URL de service incorrecte ou d’aucune URL de service mentionnée dans les services cloud Service de conversion de formulaires automatisés.<br><br>**Résolution**<br> URL [de](configure-service.md#configure-the-cloud-service) service correct dans les services Cloud du service de conversion automatisée des formulaires. | ![Impossible de se connecter au service.](assets/wrong-endpoint-configured.png) |
| **Message** d’erreur <br> Le service n’a pas pu convertir le formulaire.  <br><br>**Raison **<br>des problèmes de connectivité réseau à votre fin ou du service en panne en raison d’une maintenance ou d’une panne planifiée sur Adobe Cloud.<br><br>**Résolution** <br> Résolvez les problèmes de connectivité réseau à votre fin et vérifiez l’état du service sur https://status.adobe.com/ en cas de panne planifiée ou non. | ![Impossible de se connecter au service.](assets/service-failure.png) |
| **Message** d’erreur <br> Le nombre de pages dépasse 15.  <br><br>**Raison **<br>Le dossier contenant les formulaires XDP et PDF source contient plus de 15 fichiers.<br><br>**Résolution** <br> Portez le nombre de formulaires dans un dossier à moins de 15 ou égal à 15. Ramenez le nombre total de pages dans un dossier de moins de 50 pages. Donnez au dossier une taille inférieure à 10 Mo. Ne conservez pas les formulaires dans un sous-dossier. Organisez les  sources dans un lot de  de 8 à 15. | ![Impossible de se connecter au service.](assets/number-of-pages.png) |
| **Message** d’erreur <br> Le format du fichier source n’est pas pris en charge.  <br><br>**Raison **<br>: le dossier contenant les formulaires source contient des fichiers non pris en charge.<br><br>**Résolution** <br> Le service ne prend en charge que les fichiers .xdp et .pdf. Supprimez les fichiers avec toute autre extension du dossier et exécutez la conversion. | ![Impossible de se connecter au service.](assets/unsupported-file-formats.png) |
| **Message** <br> d’erreur Les formulaires analysés ne sont pas pris en charge.  <br><br>**Motif **<br>Le formulaire PDF contient uniquement une image numérisée du formulaire et ne contient aucune structure de contenu.<br><br>**Résolution** <br> Le service ne prend pas en charge la conversion de formulaires numérisés ou d’une image d’un formulaire en formulaire adaptatif prêt à l’emploi. Cependant, vous pouvez utiliser Adobe Acrobat pour convertir l’image d’un formulaire en un formulaire PDF. Ensuite, utilisez le service pour convertir le formulaire PDF en un formulaire adaptatif. Utilisez toujours une image de qualité pour la conversion du formulaire dans Acrobat. Cela améliore la qualité de la conversion. | ![Impossible de se connecter au service.](assets/scanned-forms-error.png) |