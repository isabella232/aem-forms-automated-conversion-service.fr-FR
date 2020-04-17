---
title: 'Dépannage du service de conversion automatisée des formulaires '
seo-title: 'Résolution des problèmes du service de conversion automatisée des formulaires (AFCS) '
description: 'Problèmes courants de l''AFCS et leurs solutions '
seo-description: Problèmes courants de l'AFCS et leurs solutions
contentOwner: khsingh
topic-tags: forms
translation-type: tm+mt
source-git-commit: 535267e20fb8e583e1c01f4160be378ffd31a4a4

---


# Dépannage du service de conversion automatisée des formulaires


<!--The article provides information on installation, configuration and administration issues that may arise in an Automated Forms Conversion Service production environment. --> The document  provides basic troubleshooting steps for common errors.

## Erreurs courantes {#commonerrors}

| Erreur | Exemple |
|--- |--- |
| **Message** d’erreur <br> L’en-tête  n’est pas disponible. <br><br>**Raison **<br>: un administrateur a créé plusieurs configurations IMS ou la configuration IMS n’est pas en mesure d’accéder au service AFCS sur Adobe Cloud.<br><br>**Résolution**<br> S&#39;il existe plusieurs configurations, supprimez toutes les configurations et [créez une nouvelle configuration](configure-service.md#obtainpubliccertificates). <br> S’il existe une configuration unique, **[!UICONTROL Health Check]** vérifiez la connectivité [](configure-service.md#createintegrationoption). | ![L&#39;en-tête  du n&#39;est pas disponible](assets/invalid-ims-configuration.png) |
| **Message** d’erreur <br> Impossible de se connecter au service.  <br><br>**Raison **<br>d’une URL de service incorrecte ou d’aucune URL de service mentionnée dans les services cloud Service de conversion de formulaires automatisés.<br><br>**Résolution**<br> URL [de](configure-service.md#configure-the-cloud-service) service correct dans les services Cloud du service de conversion automatisée des formulaires. | ![Impossible de se connecter au service.](assets/wrong-endpoint-configured.png) |
| **Message** d’erreur <br> Le service n’a pas pu convertir le formulaire.  <br><br>**Raison **<br>des problèmes de connectivité réseau à votre fin, le service est arrêté en raison d’une maintenance planifiée ou d’une panne sur Adobe Cloud.<br><br>**Résolution** <br> Résolvez les problèmes de connectivité réseau à votre fin et vérifiez l’état du service sur https://status.adobe.com/ en cas de panne planifiée ou non planifiée. | ![Impossible de se connecter au service.](assets/service-failure.png) |
| **Message** d’erreur <br> Le nombre de pages est supérieur à 15.  <br><br>**Motif **<br>Le formulaire source fait plus de 15 pages.<br><br>**Résolution** <br> Utilisez Adobe Acrobat pour scinder des formulaires de plus de 15 pages. Ramenez le nombre de pages d’un formulaire à moins de 15. | ![Impossible de se connecter au service.](assets/number-of-pages.png) |
| **Message** d’erreur <br> Le nombre de fichiers est supérieur à 15.  <br><br>**Raison **Le dossier contient plus de 15 formulaires<br>.<br><br>**Résolution** <br> Portez le nombre de formulaires dans un dossier à moins de 15 ou égal à 15. Ramenez le nombre total de pages dans un dossier de moins de 50 pages. Donnez au dossier une taille inférieure à 10 Mo. Ne conservez pas les formulaires dans un sous-dossier. Organisez les formulaires source en un lot de 8 à 15 formulaires. | ![Impossible de se connecter au service.](assets/number-of-pages.png) |
| **Message** d’erreur <br> Le format du fichier source n’est pas pris en charge.  <br><br>**Raison **<br>: le dossier contenant les formulaires source contient des fichiers non pris en charge.<br><br>**Résolution** <br> Le service ne prend en charge que les fichiers .xdp et .pdf. Supprimez les fichiers avec toute autre extension du dossier et exécutez la conversion. | ![Impossible de se connecter au service.](assets/unsupported-file-formats.png) |
| **Message** <br> d’erreur Les formulaires analysés ne sont pas pris en charge.  <br><br>**Motif **<br>Le formulaire PDF contient uniquement des images numérisées du formulaire et ne contient aucune structure de contenu.<br><br>**Résolution** <br> Le service ne prend pas en charge la conversion de formulaires numérisés ou d’une image d’un formulaire en formulaire adaptatif prêt à l’emploi. Cependant, vous pouvez utiliser Adobe Acrobat pour convertir l’image d’un formulaire en un formulaire PDF. Ensuite, utilisez le service pour convertir le formulaire PDF en un formulaire adaptatif. Utilisez toujours une image de qualité pour la conversion du formulaire dans Acrobat. Cela améliore la qualité de la conversion. | ![Impossible de se connecter au service.](assets/scanned-forms-error.png) |
| **Le formulaire PDF chiffré de message** <br> d’erreur n’est pas pris en charge.  <br><br>**Motif **<br>Le dossier contient des formulaires PDF chiffrés.<br><br>**Résolution** <br> Le service ne prend pas en charge la conversion d’un formulaire PDF chiffré en formulaire adaptatif. Supprimez le chiffrement, téléchargez le formulaire non chiffré et exécutez la conversion. | ![Impossible de se connecter au service.](assets/secured-pdf-form.png) |
| **Message** d’erreur <br> Impossible d’analyser le  JSON de méta-modèle.  <br><br>**Raison **<br>: le JSON fourni au service n’est pas correctement formaté, contient des caractères non valides ou utilise une syntaxe non valide pour mapper les composants.<br><br>**Résolution** <br> Vérifiez le formatage du fichier JSON. Vous pouvez utiliser n’importe quel validateur JSON en ligne pour vérifier la mise en forme et la structure du. Voir [Étendre l’article par défaut sur les méta-modèles](extending-the-default-meta-model.md) pour plus d’informations sur la syntaxe des méta-modèles. | ![Impossible de se connecter au service.](assets/invalid-meta-model-schema.png) |
