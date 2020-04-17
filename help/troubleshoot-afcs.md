---
title: 'Dépannage du service de conversion automatisée des formulaires '
seo-title: 'Résolution des problèmes du service de conversion automatisée des formulaires (AFCS) '
description: 'Problèmes courants de l''AFCS et leurs solutions '
seo-description: Problèmes courants de l'AFCS et leurs solutions
contentOwner: khsingh
topic-tags: forms
translation-type: tm+mt
source-git-commit: 56e4696c0372223e0b27f1c313382a2a637b6db1

---


# Dépannage du service de conversion automatisée des formulaires


<!--The article provides information on installation, configuration and administration issues that may arise in an Automated Forms Conversion Service production environment. --> The document  provides basic troubleshooting steps for common errors.

## Erreurs courantes {#commonerrors}
<!--
|Error|Example|
|--- |--- |
|**Error Message** <br> The access token header is not available. <br><br>**Reason** <br> An administrator has created multiple IMS configurations or IMS configuration is not able to reach AFCS service on Adobe Cloud. <br><br>**Resolution** <br> If there are multiple configurations, delete all the configurations and [create a new configuration](configure-service.md#obtainpubliccertificates). <br> If there is a single configuration, use **[!UICONTROL Health Check]** to [check connectivity](configure-service.md#createintegrationoption).|![The access token header is not available](assets/invalid-ims-configuration.png)|
|**Error Message** <br> Unable to connect to the service.  <br><br>**Reason** <br> Incorrect service URL or no service URL is mentioned in Automated Forms Conversion Service cloud services. <br><br>**Resolution** <br> Correct [Service URL](configure-service.md#configure-the-cloud-service) in Automated Forms Conversion Service Cloud services.|![Unable to connect to the service.](assets/wrong-endpoint-configured.png)|
|**Error Message** <br> The service failed to convert the form.  <br><br>**Reason** <br> Network connectivity issues at your end, the service is down due to scheduled maintenance, or outage on Adobe Cloud. <br><br>**Resolution** <br> Resolve network connectivity issues at your end and check the status of the service on https://status.adobe.com/ for a planned or unplanned outage.|![Unable to connect to the service.](assets/service-failure.png)|
|**Error Message** <br> The number of pages is more than 15.  <br><br>**Reason** <br> The source form is more than 15 pages long.  <br><br>**Resolution** <br> Use Adobe Acrobat to split forms with more than 15 pages. Bring the number of pages in a form to less than 15. |![Unable to connect to the service.](assets/number-of-pages.png)|
|**Error Message** <br> The number of files is more than 15.  <br><br>**Reason** <br>  The folder contains more than 15 forms. <br><br>**Resolution** <br> Bring the number of forms in a folder to less than or equal to 15. Bring the total number of pages in a folder less than 50. Bring the size of the folder to less than 10 MB. Do not keep forms in a sub-folder. Organize source forms into a batch of 8-15 forms. |![Unable to connect to the service.](assets/number-of-pages.png)|
|**Error Message** <br> The source file format is not supported.  <br><br>**Reason** <br> The folder containing source forms have some unsupported files. <br><br>**Resolution** <br> The service supports only .xdp and .pdf files. Remove files with any other extension from the folder and run the conversion. |![Unable to connect to the service.](assets/unsupported-file-formats.png)|
|**Error Message** <br> Scanned forms are not supported.  <br><br>**Reason** <br> The PDF form contains only scanned images of the form and contains no content structure. <br><br>**Resolution** <br> The service does not support converting scanned forms or an image of a form to an adaptive out-of-the-box. However, you use Adobe Acrobat to convert the image of a form to a PDF Form. Then, use the service to convert the PDF Form to an adaptive form. Always use a high-quality image of the form for conversion in Acrobat. It improves the quality of the conversion. |![Unable to connect to the service.](assets/scanned-forms-error.png)|
|**Error Message** <br> Encrypted PDF form is not supported.  <br><br>**Reason** <br> The folder contains encrypted PDF forms. <br><br>**Resolution** <br> The service does not support converting an encrypted PDF form to an adaptive form. Remove the encryption, upload the non-encrypted form, and run the conversion. |![Unable to connect to the service.](assets/secured-pdf-form.png)|
|**Error Message** <br> Unable to parse meta-model JSON schema.  <br><br>**Reason** <br> The JSON schema supplied to the service is not properly formatted, contains invalid characters, or uses invalid syntax to map components.  <br><br>**Resolution** <br> Check the formatting of the JSON file. You can use any online JSON validator to check the formatting and structure of the schema. See, [Extend the default meta-model](extending-the-default-meta-model.md) article for information on meta-model syntax. |![Unable to connect to the service.](assets/invalid-meta-model-schema.png)| -->

<table>
<thead>
<tr>
<th>Erreur</th>
<th>Exemple</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Message</strong> d’erreur <br> L’en-tête  n’est pas disponible. <br><br><strong>Raison</strong> <br> : un administrateur a créé plusieurs configurations IMS ou la configuration IMS n’est pas en mesure d’accéder au service AFCS sur Adobe Cloud. <br><br><strong>Résolution</strong><br> S'il existe plusieurs configurations, supprimez toutes les configurations et <a href="configure-service.md#obtainpubliccertificates">créez une nouvelle configuration</a>. <br> S'il existe une configuration unique, utilisez <strong>[!UICONTROL Health Check]</strong> pour <a href="configure-service.md#createintegrationoption">vérifier la connectivité</a>.</td>
<td><img alt="L'en-tête  du n'est pas disponible" src="assets/invalid-ims-configuration.png" /></td>
</tr>
<tr>
<td><strong>Message</strong> d’erreur <br> Impossible de se connecter au service.  <br><br><strong>Raison</strong> <br> d’une URL de service incorrecte ou d’aucune URL de service mentionnée dans les services cloud Service de conversion de formulaires automatisés. <br><br><strong>Résolution</strong><br> URL <a href="configure-service.md#configure-the-cloud-service">de</a> service correct dans les services Cloud du service de conversion automatisée des formulaires.</td>
<td><img alt="Impossible de se connecter au service." src="assets/wrong-endpoint-configured.png" /></td>
</tr>
<tr>
<td><strong>Message</strong> d’erreur <br> Le service n’a pas pu convertir le formulaire.  <br><br><strong>Raison</strong> <br> des problèmes de connectivité réseau à votre fin, le service est arrêté en raison d’une maintenance planifiée ou d’une panne sur Adobe Cloud. <br><br><strong>Résolution</strong><br> Résolvez les problèmes de connectivité réseau à votre fin et vérifiez l'état du service sur <a href="https://status.adobe.com/">https://status.adobe.com/</a> pour une panne planifiée ou non planifiée.</td>
<td><img alt="Le service n’a pas pu convertir le formulaire." src="assets/service-failure.png" /></td>
</tr>
<tr>
<td><strong>Message</strong> d’erreur <br> Le nombre de pages est supérieur à 15.  <br><br><strong>Motif</strong> <br> Le formulaire source fait plus de 15 pages.  <br><br><strong>Résolution</strong> <br> Utilisez Adobe Acrobat pour scinder des formulaires de plus de 15 pages. Ramenez le nombre de pages d’un formulaire à moins de 15.</td>
<td><img alt="Le nombre de pages est supérieur à 15." src="assets/number-of-pages.png" /></td>
</tr>
<tr>
<td><strong>Message</strong> d’erreur <br> Le nombre de fichiers est supérieur à 15.  <br><br><strong>Raison</strong> Le dossier contient plus de 15 formulaires <br> . <br><br><strong>Résolution</strong> <br> Portez le nombre de formulaires dans un dossier à moins de 15 ou égal à 15. Ramenez le nombre total de pages dans un dossier de moins de 50 pages. Donnez au dossier une taille inférieure à 10 Mo. Ne conservez pas les formulaires dans un sous-dossier. Organisez les formulaires source en un lot de 8 à 15 formulaires.</td>
<td><img alt="Le nombre de fichiers est supérieur à 15." src="assets/number-of-pages.png" /></td>
</tr>
<tr>
<td><strong>Message</strong> d’erreur <br> Le format du fichier source n’est pas pris en charge.  <br><br><strong>Raison</strong> <br> : le dossier contenant les formulaires source contient des fichiers non pris en charge. <br><br><strong>Résolution</strong> <br> Le service ne prend en charge que les fichiers .xdp et .pdf. Supprimez les fichiers avec toute autre extension du dossier et exécutez la conversion.</td>
<td><img alt="Le format du fichier source n’est pas pris en charge." src="assets/unsupported-file-formats.png" /></td>
</tr>
<tr>
<td><strong>Message</strong> <br> d’erreur Les formulaires analysés ne sont pas pris en charge.  <br><br><strong>Motif</strong> <br> Le formulaire PDF contient uniquement des images numérisées du formulaire et ne contient aucune structure de contenu. <br><br><strong>Résolution</strong> <br> Le service ne prend pas en charge la conversion de formulaires numérisés ou d’une image d’un formulaire en formulaire adaptatif prêt à l’emploi. Cependant, vous pouvez utiliser Adobe Acrobat pour convertir l’image d’un formulaire en un formulaire PDF. Ensuite, utilisez le service pour convertir le formulaire PDF en un formulaire adaptatif. Utilisez toujours une image de qualité pour la conversion du formulaire dans Acrobat. Cela améliore la qualité de la conversion.</td>
<td><img alt="Les formulaires numérisés ne sont pas pris en charge." src="assets/scanned-forms-error.png" /></td>
</tr>
<tr>
<td><strong>Le formulaire PDF chiffré de message</strong> <br> d’erreur n’est pas pris en charge.  <br><br><strong>Motif</strong> <br> Le dossier contient des formulaires PDF chiffrés. <br><br><strong>Résolution</strong> <br> Le service ne prend pas en charge la conversion d’un formulaire PDF chiffré en formulaire adaptatif. Supprimez le chiffrement, téléchargez le formulaire non chiffré et exécutez la conversion.</td>
<td><img alt="Le formulaire PDF chiffré n’est pas pris en charge." src="assets/secured-pdf-form.png" /></td>
</tr>
<tr>
<td><strong>Message</strong> d’erreur <br> Impossible d’analyser le  JSON de méta-modèle.  <br><br><strong>Raison</strong> <br> : le JSON fourni au service n’est pas correctement formaté, contient des caractères non valides ou utilise une syntaxe non valide pour mapper les composants.  <br><br><strong>Résolution</strong> <br> Vérifiez le formatage du fichier JSON. Vous pouvez utiliser n’importe quel validateur JSON en ligne pour vérifier la mise en forme et la structure du. Voir <a href="extending-the-default-meta-model.md">Étendre l’article par défaut sur les méta-modèles</a> pour plus d’informations sur la syntaxe des méta-modèles.</td>
<td><img alt="Impossible d'analyser le JSON de méta-modèle " src="assets/invalid-meta-model-schema.png" /></td>
</tr>
</tbody>
</table>
