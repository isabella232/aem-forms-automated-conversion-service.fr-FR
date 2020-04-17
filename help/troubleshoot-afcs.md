---
title: 'Dépannage du service de conversion automatisée des formulaires '
seo-title: 'Résolution des problèmes du service de conversion automatisée des formulaires (AFCS) '
description: 'Problèmes courants de l''AFCS et leurs solutions '
seo-description: Problèmes courants de l'AFCS et leurs solutions
contentOwner: khsingh
topic-tags: forms
translation-type: tm+mt
source-git-commit: 3a82102feffa7fc618dc37c9a745c254a46a0700

---


# Dépannage du service de conversion automatisée des formulaires


<!--The article provides information on installation, configuration and administration issues that may arise in an Automated Forms Conversion Service production environment. --> The document  provides basic troubleshooting steps for common errors.

## Erreurs courantes {#commonerrors}

| Erreur | Exemple |
|--- |--- |
| **Message** d’erreur <br> L’en-tête  n’est pas disponible. <br><br> **Raison** <br> : un administrateur a créé plusieurs configurations IMS ou la configuration IMS n’est pas en mesure d’accéder au service AFCS sur Adobe Cloud. <br><br>**Résolution **<br>S&#39;il existe plusieurs configurations, supprimez toutes les configurations et[créez une nouvelle configuration](configure-service.md#obtainpubliccertificates).<br>S’il existe une configuration unique, utilisez** Health Check **pour[vérifier la connectivité](configure-service.md#createintegrationoption). | ![L&#39;en-tête  du n&#39;est pas disponible](assets/invalid-ims-configurations.png) |

| Erreur | Exemple |
|--- |--- |
| **Message** d’erreur <br> Impossible de se connecter au service.  <br><br>**Raison **<br>d’une URL de service incorrecte ou d’aucune URL de service mentionnée dans les services cloud Service de conversion de formulaires automatisés.<br><br>**Résolution**<br> URL [de](configure-service.md#configure-the-cloud-service) service correct dans les services Cloud du service de conversion automatisée des formulaires. | ![Impossible de se connecter au service.](assets/wrong-endpoint-configured.png) |
| **Message** d’erreur <br> Le service n’a pas pu convertir le formulaire.  <br><br>**Raison **<br>des problèmes de connectivité réseau à votre fin, le service est arrêté en raison d’une maintenance planifiée ou d’une panne sur Adobe Cloud.<br><br>**Résolution** <br> Résolvez les problèmes de connectivité réseau à votre fin et vérifiez l’état du service sur https://status.adobe.com/ en cas de panne planifiée ou non planifiée. | ![Impossible de se connecter au service.](assets/service-failure.png) |
| **Message** d’erreur <br> Le nombre de pages est supérieur à 15.  <br><br>**Motif **<br>Le formulaire source fait plus de 15 pages.<br><br>**Résolution** <br> Utilisez Adobe Acrobat pour scinder des formulaires de plus de 15 pages. Ramenez le nombre de pages d’un formulaire à moins de 15. | ![Impossible de se connecter au service.](assets/number-of-pages.png) |
| **Message** d’erreur <br> Le nombre de fichiers est supérieur à 15.  <br><br>**Raison **Le dossier contient plus de 15 formulaires<br>.<br><br>**Résolution** <br> Portez le nombre de formulaires dans un dossier à moins de 15 ou égal à 15. Ramenez le nombre total de pages dans un dossier de moins de 50 pages. Donnez au dossier une taille inférieure à 10 Mo. Ne conservez pas les formulaires dans un sous-dossier. Organisez les formulaires source en un lot de 8 à 15 formulaires. | ![Impossible de se connecter au service.](assets/number-of-pages.png) |
| **Message** d’erreur <br> Le format du fichier source n’est pas pris en charge.  <br><br>**Raison **<br>: le dossier contenant les formulaires source contient des fichiers non pris en charge.<br><br>**Résolution** <br> Le service ne prend en charge que les fichiers .xdp et .pdf. Supprimez les fichiers avec toute autre extension du dossier et exécutez la conversion. | ![Impossible de se connecter au service.](assets/unsupported-file-formats.png) |
| **Message** <br> d’erreur Les formulaires analysés ne sont pas pris en charge.  <br><br>**Motif **<br>Le formulaire PDF contient uniquement des images numérisées du formulaire et ne contient aucune structure de contenu.<br><br>**Résolution** <br> Le service ne prend pas en charge la conversion de formulaires numérisés ou d’une image d’un formulaire en formulaire adaptatif prêt à l’emploi. Cependant, vous pouvez utiliser Adobe Acrobat pour convertir l’image d’un formulaire en un formulaire PDF. Ensuite, utilisez le service pour convertir le formulaire PDF en un formulaire adaptatif. Utilisez toujours une image de qualité pour la conversion du formulaire dans Acrobat. Cela améliore la qualité de la conversion. | ![Impossible de se connecter au service.](assets/scanned-forms-error.png) |
| **Le formulaire PDF chiffré de message** <br> d’erreur n’est pas pris en charge.  <br><br>**Motif **<br>Le dossier contient des formulaires PDF chiffrés.<br><br>**Résolution** <br> Le service ne prend pas en charge la conversion d’un formulaire PDF chiffré en formulaire adaptatif. Supprimez le chiffrement, téléchargez le formulaire non chiffré et exécutez la conversion. | ![Impossible de se connecter au service.](assets/secured-pdf-form.png) |
| **Message** d’erreur <br> Impossible d’analyser le  JSON de méta-modèle.  <br><br>**Raison **<br>: le JSON fourni au service n’est pas correctement formaté, contient des caractères non valides ou utilise une syntaxe non valide pour mapper les composants.<br><br>**Résolution** <br> Vérifiez le formatage du fichier JSON. Vous pouvez utiliser n’importe quel validateur JSON en ligne pour vérifier la mise en forme et la structure du. Voir [Étendre l’article par défaut sur les méta-modèles](extending-the-default-meta-model.md) pour plus d’informations sur la syntaxe des méta-modèles. | ![Impossible de se connecter au service.](assets/invalid-meta-model-schema.png) |

<!--

<table>
<thead>
<tr>
<th>Error</th>
<th>Example</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Error Message</strong> <p> The access token header is not available. </p><br><strong>Reason</strong> <br> An administrator has created multiple IMS configurations or IMS configuration is not able to reach AFCS service on Adobe Cloud. <br><br><strong>Resolution</strong> <br> If there are multiple configurations, delete all the configurations and <a href="configure-service.md#obtainpubliccertificates">create a new configuration</a>. <br> If there is a single configuration, use <strong> Health Check </strong> to <a href="configure-service.md#createintegrationoption">check connectivity</a>.</td>
<td><img alt="The access token header is not available" src="assets/invalid-ims-configuration.png" /></td>
</tr>
<tr>
<td><strong>Error Message</strong> <br> Unable to connect to the service.  <br><br><strong>Reason</strong> <br> Incorrect service URL or no service URL is mentioned in Automated Forms Conversion Service cloud services. <br><br><strong>Resolution</strong> <br> Correct <a href="configure-service.md#configure-the-cloud-service">Service URL</a> in Automated Forms Conversion Service Cloud services.</td>
<td><img alt="Unable to connect to the service." src="assets/wrong-endpoint-configured.png" /></td>
</tr>
<tr>
<td><strong>Error Message</strong> <br> The service failed to convert the form.  <br><br><strong>Reason</strong> <br> Network connectivity issues at your end, the service is down due to scheduled maintenance, or outage on Adobe Cloud. <br><br><strong>Resolution</strong> <br> Resolve network connectivity issues at your end and check the status of the service on <a href="https://status.adobe.com/">https://status.adobe.com/</a> for a planned or unplanned outage.</td>
<td><img alt="The service failed to convert the form." src="assets/service-failure.png" /></td>
</tr>
<tr>
<td><strong>Error Message</strong> <br> The number of pages is more than 15.  <br><br><strong>Reason</strong> <br> The source form is more than 15 pages long.  <br><br><strong>Resolution</strong> <br> Use Adobe Acrobat to split forms with more than 15 pages. Bring the number of pages in a form to less than 15.</td>
<td><img alt="The number of pages is more than 15." src="assets/number-of-pages.png" /></td>
</tr>
<tr>
<td><strong>Error Message</strong> <br> The number of files is more than 15.  <br><br><strong>Reason</strong> <br>  The folder contains more than 15 forms. <br><br><strong>Resolution</strong> <br> Bring the number of forms in a folder to less than or equal to 15. Bring the total number of pages in a folder less than 50. Bring the size of the folder to less than 10 MB. Do not keep forms in a sub-folder. Organize source forms into a batch of 8-15 forms.</td>
<td><img alt="The number of files is more than 15." src="assets/number-of-pages.png" /></td>
</tr>
<tr>
<td><strong>Error Message</strong> <br> The source file format is not supported.  <br><br><strong>Reason</strong> <br> The folder containing source forms have some unsupported files. <br><br><strong>Resolution</strong> <br> The service supports only .xdp and .pdf files. Remove files with any other extension from the folder and run the conversion.</td>
<td><img alt="The source file format is not supported." src="assets/unsupported-file-formats.png" /></td>
</tr>
<tr>
<td><strong>Error Message</strong> <br> Scanned forms are not supported.  <br><br><strong>Reason</strong> <br> The PDF form contains only scanned images of the form and contains no content structure. <br><br><strong>Resolution</strong> <br> The service does not support converting scanned forms or an image of a form to an adaptive out-of-the-box. However, you use Adobe Acrobat to convert the image of a form to a PDF Form. Then, use the service to convert the PDF Form to an adaptive form. Always use a high-quality image of the form for conversion in Acrobat. It improves the quality of the conversion.</td>
<td><img alt="Scanned forms are not supported." src="assets/scanned-forms-error.png" /></td>
</tr>
<tr>
<td><strong>Error Message</strong> <br> Encrypted PDF form is not supported.  <br><br><strong>Reason</strong> <br> The folder contains encrypted PDF forms. <br><br><strong>Resolution</strong> <br> The service does not support converting an encrypted PDF form to an adaptive form. Remove the encryption, upload the non-encrypted form, and run the conversion.</td>
<td><img alt="Encrypted PDF form is not supported." src="assets/secured-pdf-form.png" /></td>
</tr>
<tr>
<td><strong>Error Message</strong> <br> Unable to parse meta-model JSON schema.  <br><br><strong>Reason</strong> <br> The JSON schema supplied to the service is not properly formatted, contains invalid characters, or uses invalid syntax to map components.  <br><br><strong>Resolution</strong> <br> Check the formatting of the JSON file. You can use any online JSON validator to check the formatting and structure of the schema. See, <a href="extending-the-default-meta-model.md">Extend the default meta-model</a> article for information on meta-model syntax.</td>
<td><img alt="Unable to parse meta-model JSON schema" src="assets/invalid-meta-model-schema.png" /></td>
</tr>
</tbody>
</table>
-->