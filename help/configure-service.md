---
title: Configuration du service de conversion de formulaires automatisés
description: Prêt de votre instance AEM à utiliser le service de conversion de formulaires automatisés
translation-type: tm+mt
source-git-commit: 01dfd20951314017d47713bfb1a2a5f2d563f434

---


# Configuration du service de conversion de formulaires automatisés {#about-this-help}

Cette aide décrit comment un administrateur AEM peut configurer le service de conversion automatisée des formulaires pour automatiser la conversion de ses formulaires PDF en formulaires adaptatifs. Cette aide est destinée aux administrateurs informatiques et AEM de votre entreprise. Cette aide s’adresse à un public familiarisé avec les technologies suivantes :

* Installation, configuration et administration des packages Adobe Experience Manager et AEM,

* Utilisation des systèmes d&#39;exploitation Linux et Microsoft Windows,

* Configuration des serveurs de messagerie SMTP

>[!VIDEO](https://video.tv.adobe.com/v/29267/)

**Regardez la vidéo ou lisez l’article pour configurer le service de conversion automatisée des formulaires.**

## Intégration{#onboarding}

Ce service est disponible gratuitement pour les clients de longue durée d’AEM Forms 6.4 et d’AEM Forms 6.5 sur site et les clients d’entreprise du service géré Adobe. Vous pouvez contacter l’équipe commerciale d’Adobe ou votre représentant Adobe pour demander l’accès au service.

Adobe permet d’accéder à votre organisation et de fournir les privilèges requis à la personne désignée comme administrateur dans votre organisation. L’administrateur peut accorder l’accès aux développeurs (utilisateurs) d’AEM Forms de votre organisation pour la connexion au service.

## Conditions préalables {#prerequisites}

Pour utiliser le service de conversion automatisée des formulaires, vous devez disposer des éléments suivants :

* Le service de conversion automatisée des formulaires est activé pour votre entreprise
* Un compte Adobe ID doté de droits d’administrateur pour le service de conversion
* Une instance d’auteur AEM 6.4 ou AEM 6.5 opérationnelle avec la dernière version d’AEM Service Pack
* Utilisateur AEM (sur votre instance AEM) membre du groupe d’utilisateurs de formulaires

## Configuration du  {#setuptheservice}

Avant d’utiliser le service, préparez votre instance d’auteur AEM pour vous connecter au service en cours d’exécution sur Adobe Cloud. Effectuez les étapes suivantes dans la séquence répertoriée pour préparer votre instance pour le service :

1. [Téléchargement et installation d’AEM 6.4 ou d’AEM 6.5](#aemquickstart)
1. [Téléchargement et installation de la dernière version d’AEM Service Pack](#servicepack)
1. [Téléchargement et installation des derniers modules complémentaires d’AEM Forms](#downloadaemformsaddon)
1. [Téléchargement et installation des derniers packages de connecteur](#installConnectorPackage)
1. [Création de  et de modèles personnalisés](#referencepackage)

### Téléchargement et installation d’AEM 6.4 ou d’AEM 6.5 {#aemquickstart}


Le service de conversion automatisée des formulaires s’exécute sur l’instance d’auteur AEM. Vous avez besoin d’AEM 6.4 ou d’AEM 6.5 pour configurer une instance d’auteur AEM. Si AEM n’est pas en cours d’exécution, téléchargez-le à partir des emplacements suivants :

* Si vous êtes déjà client AEM, téléchargez AEM 6.4 ou AEM 6.5 depuis le site Web [d’achat de licences](http://licensing.adobe.com)Adobe.

* Si vous êtes un partenaire Adobe, utilisez le [de formation des partenaires](https://adobe.allegiancetech.com/cgi-bin/qwebcorporate.dll?idx=82357Q) Adobe pour demander AEM 6.4 ou AEM 6.5.

Après avoir téléchargé AEM, pour obtenir des instructions sur la configuration d’une instance d’auteur AEM, voir [Déploiement et maintenance](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/deploy.html#defaultlocalinstall).

### Download and install AEM latest Service Pack {#servicepack}

Téléchargez et installez la dernière version d’AEM Service Pack. Pour obtenir des instructions détaillées, reportez-vous à la page Notes [de mise à jour d’](https://helpx.adobe.com/experience-manager/6-4/release-notes/sp-release-notes.html) AEM 6.4 Service Pack ou Notes [de mise à jour d’](https://helpx.adobe.com/experience-manager/6-5/release-notes/sp-release-notes.html)AEM 6.5 Service Pack.

### Download and install AEM Forms add-on package  {#downloadaemformsaddon}

Une instance AEM contient les fonctionnalités de base des formulaires. Le service de conversion nécessite des fonctionnalités complètes d’AEM Forms. Téléchargez et installez le module complémentaire AEM Forms pour bénéficier de toutes les fonctionnalités d’AEM Forms. Le package est requis pour configurer et exécuter le service de conversion. Pour obtenir des instructions détaillées, voir [Installation et configuration des fonctionnalités de capture de données.](https://helpx.adobe.com/experience-manager/6-5/forms/using/installing-configuring-aem-forms-osgi.html)

>[!NOTE]
> Assurez-vous d’effectuer les configurations post-installation obligatoires après l’installation du module complémentaire.


### Téléchargement et installation du module Connector {#installConnectorPackage}

Vous avez besoin du module connecteur version 1.1.38 ou ultérieure pour utiliser les dernières fonctionnalités et améliorations fournies dans la version AFC-2020.03.1. Vous pouvez télécharger le package de connecteur à partir du partage de package AEM.

| Système d’exploitation | Lien de téléchargement du package Connector |
| ------------- | ------------- |
| Microsoft Windows | https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq650/servicepack/fd/AEM-Forms-6.5.4.0-WIN |
| Linux | https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq650/servicepack/fd/AEM-Forms-6.5.4.0-WIN |

>[!NOTE]
> Si vous disposez déjà d’un de service de conversion automatisée des formulaires en cours d’exécution, pour utiliser les dernières fonctionnalités du service de conversion, installez le dernier Service Pack, le dernier module complémentaire AEM Forms et le dernier module connecteur dans l’ordre mentionné.


### Création de  et de modèles personnalisés {#referencepackage}

Si vous  AEM en mode [de](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/production-ready.html) production (mode d’exécution nosamplecontent), les packages de référence ne sont pas installés. Les packages de référence contiennent des exemples de  et de modèles. Le service de conversion automatisée des formulaires requiert au moins un thème et un modèle pour convertir un formulaire PDF en formulaire adaptatif. Créez un thème et un modèle personnalisés de votre propre configuration [de](#configure-the-cloud-service) service point et de votre propre configuration pour utiliser des modèles et des  personnalisés avant d’utiliser le service.

## Configure the service {#configure-the-service}

Avant de procéder à la configuration du service et de connecter votre instance locale au service en cours d’exécution sur Adobe Cloud, découvrez les personnes et les privilèges requis pour vous connecter au service. Le service utilise deux types de personnalité, les administrateurs et les développeurs :

* **Administrateurs**: Les administrateurs sont responsables de la gestion des logiciels et services Adobe pour leur entreprise. Les administrateurs autorisent les développeurs de leur entreprise à se connecter au service de conversion automatisée des formulaires s’exécutant sur Adobe Cloud. Lorsqu’un administrateur est configuré pour une organisation, il reçoit un courrier électronique avec le titre **[!UICONTROL 'You now have administrator rights to manage Adobe software and services for your organization']**. Si vous êtes un administrateur, recherchez dans votre boîte aux lettres un courrier électronique avec le titre mentionné ci-dessus et passez à l’ [octroi de l’accès aux développeurs de votre organisation](#adduseranddevs).

![adresse électronique d’octroi d’accès administrateur](assets/admin-console-adobe-io-access-grantedx75.png)

* **Développeurs**: Un développeur connecte une instance d’auteur AEM Forms locale au service de conversion automatisée des formulaires s’exécutant sur Adobe Cloud. Lorsqu’un administrateur octroie des droits à un développeur pour se connecter au service de conversion automatisée des formulaires, un courrier électronique avec le titre Vous disposez maintenant des droits d’accès des développeurs pour gérer les intégrations d’API Adobe pour votre entreprise est envoyé au développeur. Si vous êtes un développeur, recherchez dans votre boîte aux lettres un courrier électronique avec le titre mentionné ci-dessus et passez à la section [Connexion de votre instance locale AEM au service de conversion automatisée des formulaires sur Adobe Cloud.](#connectafcadobeio)

![adresse électronique d’octroi d’accès aux développeurs](assets/email-developer-accessx94.png)

### (Pour les administrateurs uniquement) Accordez l’accès aux développeurs de votre entreprise {#adduseranddevs}

Une fois qu’Adobe a activé l’accès pour votre entreprise et accordé les privilèges requis à l’administrateur, l’administrateur peut se connecter à la console d’administration (instructions détaillées ci-dessous), créer un  et ajouter des développeurs au  de. Les développeurs peuvent connecter une instance locale d’AEM Forms au service de conversion automatisée des formulaires sur Adobe Cloud.

Les développeurs sont des membres de votre organisation désignés pour exécuter le service de conversion. Seuls les développeurs qui sont ajoutés au de service de conversion automatisée des formulaires Adobe sont autorisés à utiliser le service de conversion automatisée des formulaires. Effectuez les étapes ci-dessous pour créer un  et y ajouter des développeurs :

1. Connectez-vous à la Console [d’administration](https://adminconsole.adobe.com/). Utilisez l’ID **** Adobe de l’administrateur configuré pour utiliser le service de conversion automatisée des formulaires pour vous connecter. N’utilisez pas d’autre ID ou Federated ID pour vous connecter.
1. Cliquez sur l’ **[!UICONTROL Automated Forms Conversion]** option.
1. Cliquez sur **[!UICONTROL New Profile]** dans l’ **[!UICONTROL Products]** onglet.
1. Spécifiez **[!UICONTROL Name]**, **[!UICONTROL Display Name]** et **[!UICONTROL Description]** le  du. Cliquez sur **[!UICONTROL Done]**. Un  est créé.

   ![Spécifiez les détails du nouveau  de.](assets/create-new-profile-details.png)

1. Ajouter développeur au . Pour ajouter les développeurs :
   1. Dans la console [d’administration](https://adminconsole.adobe.com/enterprise), accédez à l’onglet Aperçu.
   1. Cliquez sur **[!UICONTROL Assign Developers]** la carte de produit requise.
   1. Entrez l’adresse électronique des développeurs et, éventuellement, les prénoms et les noms de famille.
   1. Sélectionnez  de produit. Appuyer **[!UICONTROL Save]**.

Répétez les étapes ci-dessus pour tous les utilisateurs.  Pour plus d’informations sur l’ajout de développeurs, voir [Gestion des développeurs](https://helpx.adobe.com/enterprise/using/manage-developers.html).

Une fois qu’un administrateur ajoute des développeurs aux  d’E/S Adobe, les développeurs en sont avertis par courrier électronique. Après avoir reçu le courrier électronique, les développeurs peuvent procéder à la [connexion d’une instance locale d’AEM Forms au service de conversion automatisée des formulaires sur Adobe Cloud](#connectafcadobeio).

### (Pour les développeurs uniquement) Connectez votre instance locale d’AEM Forms au service de conversion de formulaires automatisés sur Adobe Cloud. {#connectafcadobeio}

Une fois qu’un administrateur vous a accordé l’accès aux développeurs, vous pouvez connecter votre instance locale d’AEM Forms au service de conversion de formulaires automatisés s’exécutant sur Adobe Cloud. Effectuez les étapes suivantes dans la séquence répertoriée pour connecter votre instance AEM Forms au service :

* [Configuration des notifications par courrier électronique](configure-service.md#configureemailnotification)
* [Ajouter l’utilisateur au groupe d’utilisateurs de formulaires](#adduserstousergroup)
* [Obtention de certificats publics](#obtainpubliccertificates)
* [Création de l’intégration Adobe I/O](#createintegration)
* [Configuration du service cloud](configure-service.md#configure-the-cloud-service)

#### Configuration de la notification par courrier électronique {#configureemailnotification}

Le service de conversion automatisée des formulaires utilise le service de messagerie Day CQ pour envoyer des notifications par courrier électronique. Ces notifications par courrier électronique contiennent des informations sur les conversions réussies ou ayant échoué. Si vous choisissez de ne pas recevoir de notification, ignorez ces étapes. Effectuez les étapes suivantes pour configurer le service Day CQ Mail :

1. Accédez au gestionnaire de configuration AEM à l’adresse `http://localhost:4502/system/console/configMgr`
1. Ouvrez la configuration du Service de messagerie Day CQ. Spécifiez une valeur pour les champs **[!UICONTROL SMTP server host name]**, **[!UICONTROL SMTP server port]** et **[!UICONTROL From address]** . Cliquez sur **[!UICONTROL Save]**.

   Vous pouvez contacter votre de messagerie ou votre administrateur informatique pour plus d’informations sur le nom d’hôte et le port du serveur SMTP. Vous pouvez utiliser n’importe quelle adresse électronique valide dans le champ De. Par exemple, notification@example.com ou donotreply@example.com.

1. Open the **[!UICONTROL Day CQ Link Externalizer]** configuration. In the **[!UICONTROL Domains]** field, specify the actual host name or IP address and port number for local, author, and publish instances. Cliquez sur **[!UICONTROL Save]**.

#### Ajouter l’utilisateur au groupe d’utilisateurs de formulaires {#adduserstousergroup}

Indiquez une adresse électronique dans le  de l’utilisateur AEM désigné pour exécuter le service. Assurez-vous que l’utilisateur est membre du groupe d’utilisateurs [de](https://helpx.adobe.com/experience-manager/6-4/forms/using/forms-groups-privileges-tasks.html) formulaires. Les courriers électroniques sont envoyés à l’adresse électronique de l’utilisateur qui effectue la conversion. Pour spécifier une adresse électronique pour l’utilisateur et l’ajouter au groupe d’utilisateurs de formulaires :

1. Connectez-vous à votre instance d’auteur AEM Forms en tant qu’administrateur AEM. Utilisez vos informations d’identification AEM locales pour vous connecter. N’utilisez pas l’ID Adobe pour vous connecter. Appuyer **[!UICONTROL Adobe Experience Manager]** > **[!UICONTROL Tools]** > **[!UICONTROL Security]** > **[!UICONTROL Users]**.

1. Sélectionnez un utilisateur désigné pour exécuter le service de conversion et appuyez sur **[!UICONTROL Properties]**. La page Modifier les paramètres utilisateur s’affiche.
1. Indiquez une adresse électronique dans le **[!UICONTROL Email]** champ et appuyez sur **[!UICONTROL Save]**. Les courriers électroniques sont envoyés à l’adresse électronique spécifiée en cas d’achèvement ou d’échec de la conversion.
1. Tap the **Groups** tab. Dans l’onglet de sélection de groupe, saisissez et sélectionnez le groupe **forms-users** . Tap **Save &amp; Close**. L’utilisateur est désormais membre du groupe des utilisateurs de formulaires.

#### Obtention de certificats publics {#obtainpubliccertificates}

Un certificat public permet d’authentifier votre profil sur Adobe I/O.

1. Connectez-vous à votre instance d’auteur AEM Forms. Accédez à **[!UICONTROL Tools]**> **[!UICONTROL Security]** > **[!UICONTROL Adobe IMS Configurations]**. Appuyer **[!UICONTROL Create]**. The **[!UICONTROL Adobe IMS Technical Account Configuration]** page appears.

   ![Page Configuration du compte technique Adobe IMS](assets/adobe-ims-technical-account-configuration.png)

1. Sélectionnez **[!UICONTROL Automated Forms Conversion Service]** dans la solution Cloud.

1. Cochez la **[!UICONTROL Create new certificate]** case et spécifiez un alias. L’alias sert de nom à la boîte de dialogue. Appuyer **[!UICONTROL Create certificate]**. Une boîte de dialogue s’affiche. Cliquez sur **[!UICONTROL OK]**. Le certificat est créé.

1. Appuyez sur **[!UICONTROL Download Public Key]** et enregistrez le fichier de certificat *AEM-Adobe-IMS.crt* sur votre ordinateur. Le fichier de certificat est utilisé pour [créer l’intégration sur la console](#createintegration)d’E/S Adobe. Appuyer **[!UICONTROL Next]**.

1. Spécifiez ce qui suit :

   * Titre : Spécifiez un titre.
   * Authorization Server: [https://ims-na1.adobelogin.com](https://ims-na1.adobelogin.com)
   Laissez les autres champs vides pour l’instant (pour les remplir ultérieurement). Garde la page ouverte.

   <!--
   Comment Type: draft

   <li> </li>
   -->

   <!--
   Comment Type: draft

   <li>Step text</li>
   -->

#### Création de l’intégration Adobe I/O {#createintegration}

Pour utiliser le service de conversion automatisée des formulaires, créez une intégration dans les E/S Adobe. L’intégration génère une clé API, une clé secrète client, une charge utile (JWT).

1. Connectez-vous à [https://console.adobe.io/](https://console.adobe.io/). Utilisez votre ID Adobe, compte de développeur que votre administrateur a configuré pour vous connecter à la console d’E/S Adobe pour vous connecter.

1. Appuyer **[!UICONTROL View Integrations]**. Un écran contenant toutes les intégrations disponibles s’affiche.
1. Sélectionnez votre organisation dans la liste déroulante sous **[!UICONTROL Integrations]**. Appuyez sur **[!UICONTROL New Integration]**, sélectionnez **[!UICONTROL Access an API]**, puis appuyez **[!UICONTROL Continue]**.
1. Sélectionnez **[!UICONTROL Experience Cloud]** > **[!UICONTROL Automated Forms Conversion]** et appuyez **[!UICONTROL Continue]**. Si l’option Conversion automatisée des formulaires est désactivée pour vous, assurez-vous que vous avez sélectionné l’organisation appropriée dans la liste déroulante au-dessus de l’ **[!UICONTROL Adobe Services]** option. Si vous ne connaissez pas votre organisation, contactez votre administrateur.

   ![Sélectionner la conversion automatisée des formulaires](assets/create-new-integration.png)

1. Indiquez le nom et la description de l’intégration. Appuyez sur **[!UICONTROL Select a File from your computer]** et téléchargez le fichier AEM-Adobe-IMS.crt téléchargé dans la section [Obtenir des certificats](#obtainpubliccertificates) publics.
1. Sélectionnez le  créé lors de l’ [octroi d’un accès aux développeurs de votre organisation](#adduseranddevs) et appuyez sur **[!UICONTROL Create Integration]**. L’integration est créée.
1. Appuyez **[!UICONTROL Continue to integration details]** sur pour les informations d’intégration. La page contient la clé d’API, la clé secrète client et d’autres informations requises pour connecter votre instance locale AEM au service de conversion automatisée des formulaires. Les informations de la page sont utilisées pour créer la configuration IMS sur votre ordinateur local.

   ![Clé d’API, clé secrète client et informations de charge utile d’une intégration](assets/integration-details.png)

1. Ouvrez la page Configuration IMS sur votre instance locale. Vous avez gardé la page ouverte à la fin de la section, [Obtenez un certificat](#obtainpubliccertificates)public.

   ![Spécifier le titre, la clé d’API, la clé secrète client et la charge utile ](assets/ims-configuration-details.png)

1. Dans la page technique d’Adobe IMS, spécifiez la clé d’API et la clé secrète client. Utilisez les valeurs spécifiées sur la page d’intégration.

   **Pour la charge utile, utilisez le code fourni dans l’onglet JWT de la page d’intégration.** Appuyer  **[!UICONTROL Save]**. La configuration IMS est créée. Fermez la page d’intégration.

   ![Utiliser les valeurs du champ JWT pour le champ de charge utile](assets/jwt.png)

   >[!CAUTION]
   >
   >Créez une seule configuration IMS. Ne créez pas plus d’une configuration IMS.

1. Sélectionnez la configuration IMS et appuyez sur **[!UICONTROL Check Health]**. Une boîte de dialogue s’affiche. Appuyer **[!UICONTROL Check]**. Une fois la connexion établie, le message *Jeton récupéré* s’affiche.

   ![Une fois la connexion établie, le message du jeton récupéré s’affiche. ](assets/health-check.png)

   <br/> <br/>

#### Configure the cloud service {#configure-the-cloud-service}

Créez une configuration de service cloud pour connecter votre instance AEM au service de conversion. Il vous permet également de spécifier un modèle, un thème et des fragments de formulaire pour une conversion. Vous pouvez créer plusieurs configurations de service Cloud distinctes pour chaque jeu de formulaires. Par exemple, vous pouvez avoir une configuration distincte pour les formulaires du service des ventes et une configuration distincte pour les formulaires d’assistance clientèle. Pour créer une configuration de service cloud, procédez comme suit :

1. Sur votre instance AEM Forms, appuyez sur **[!UICONTROL Adobe Experience Manager]** > **[!UICONTROL Tools]**> **[!UICONTROL Cloud Services]** > **[!UICONTROL Automate Forms Conversion Configuration]**.
1. Appuyez sur le **[!UICONTROL Global]** dossier et appuyez sur **[!UICONTROL Create]**. La page de création de la configuration de conversion automatisée des formulaires s’affiche. La configuration est créée dans le dossier Global. Vous pouvez également créer la configuration dans un dossier différent qui existe déjà ou créer un dossier pour vos configurations.

1. Sur la **[!UICONTROL Create Automated Forms Conversion Configuration]** page, spécifiez la valeur des champs suivants et appuyez sur **[!UICONTROL Next]**.

   | Champ | Description |
   |--- |--- |
   | Titre | Titre unique de la configuration. Le titre s’affiche dans l’interface utilisateur utilisée pour  la conversion. |
   | Nom | Nom unique de la configuration. La configuration est enregistrée dans CRX-Repository avec le nom spécifié. Le nom peut être identique au titre. |
   | Emplacement de la miniature | Emplacement de la miniature pour la configuration. |
   | URL du service | URL du service de conversion de formulaires automatisés sur Adobe Cloud. Utilisez l’ `https://aemformsconversion.adobe.io/` URL. |
   | Modèle | Modèle par défaut à appliquer aux formulaires convertis. Vous pouvez toujours spécifier un modèle différent avant de commencer la conversion. Un modèle contient la structure de base et le contenu initial d’un formulaire adaptatif. Vous pouvez choisir un modèle parmi les modèles fournis prêts à l’emploi. Vous pouvez également créer un modèle personnalisé. |
   | Thème | Thème par défaut à appliquer aux formulaires convertis. Vous pouvez toujours spécifier un thème différent avant de commencer la conversion.  Vous pouvez cliquer sur l’icône pour choisir un thème fourni dans la zone. Vous pouvez également créer un thème personnalisé. |
   | Fragments existants | Emplacement des fragments existants, le cas échéant. |
   | Meta-model personnalisé | Chemin du fichier ..json du méta-modèle personnalisé. |



1. Dans l’ **[!UICONTROL Advanced]** onglet de la **[!UICONTROL Create Automated Forms Conversion Configuration]** page, spécifiez la valeur du champ suivant :

   <table>
   <thead>
   <tr>
   <th>Champ</th>
   <th>Description</th>
   </tr>
   </thead>
   <tbody>
   <tr>
   <td >Générer un document d’enregistrement</td>
   <td>Sélectionnez l’option permettant de générer automatiquement des  d’enregistrement pour les formulaires convertis. Cette option est uniquement disponible pour les formulaires XFA (formulaires XDP et PDF). Lorsque vous activez l’option, après avoir envoyé un formulaire, vous pouvez permettre à vos clients de conserver un enregistrement, sous forme imprimée ou , des informations qu’ils ont renseignées dans le formulaire pour référence ultérieure. On parle ici de document d’enregistrement.</td>
   </tr>
   <tr>
   <td>Activer les analyses</td>
   <td>Sélectionnez l’option permettant d’activer Adobe Analytics sur tous les formulaires convertis. Avant d’utiliser cette option, assurez-vous qu’Adobe Analytics est activé pour votre instance AEM Forms.</td>
   </tr>
   </tbody>
   </table>

   * Lorsque la source est un formulaire XFA avec l’extension .XDP, le DOR de sortie conserve la disposition XFA ; dans le cas contraire, le service de conversion utilise un modèle prêt à l’emploi pour générer un DOR pour d’autres formulaires XFA.
   * Lorsqu’un formulaire XFA est envoyé, les données d’envoi du formulaire sont enregistrées en tant qu’élément XML ou attribut. Par exemple, `<Amount currency="USD"> 10.00 </Amount>`. La devise est enregistrée en tant qu’attribut et le montant en devise, 10,00 est enregistré en tant qu’élément. Les données d’envoi d’un formulaire adaptatif ne comportent pas d’attributs, mais uniquement des éléments. Ainsi, lorsqu’un formulaire XFA est converti en formulaire adaptatif, les données d’envoi du formulaire adaptatif contiennent un élément pour chaque attribut de ce type. Par exemple :

   ```css
      {
         "Type": "Principal",
   
         "Amount": "10.00",
   
         "currency": "USD"
      }
   ```

1. Appuyer **[!UICONTROL Create]**. La configuration du cloud est créée. Votre instance AEM Forms est prête à  la conversion de formulaires hérités en formulaires adaptatifs.
