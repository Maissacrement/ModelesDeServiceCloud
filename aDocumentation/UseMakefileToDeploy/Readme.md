# Comment cela fonctionne

Pour simplifier l'installation d'Ansible et de ses modules associés pour Azure et GCP, nous avons mis en place un conteneur Docker préconfiguré. Ce conteneur, principalement destiné à Ansible, prend en charge les providers cloud GCP et Azure. Vous pouvez trouver l'image Docker sous le nom [ansibledind](https://github.com/Maissacrement/azureDeploy) sur GitHub et également en tant qu'artifact sur [DockerHub](https://hub.docker.com/r/maissacrement/ansibledind) avec le nom d'image docker.io/maissacrement/ansibledind:latest.

# Workflow

Avant chaque déploiement, un cycle de vie des secrets est initié dans un conteneur lancé en arrière-plan. Une fois le conteneur démarré, un script Ansible est exécuté à l'intérieur, avec le fichier de déploiement par défaut ciblé par le makefile, deploy.yml.

# Structure du repertoire de travail

```bash
Service proposé par les providers cloud gcp et azure
CLOUD_PROVIDERS_SERVICES
├── README.md
├── services_name
│   ├── gcp
|   │   ├── deploy.yml
|   │   ├── .env # Vos secret
|   │   ├── account
|   |   │   ├── my-account.json # Complement de secrets
|   ├── azure
|   │   ├── deploy.yml
|   │   ├── .env # Vos secret
│   ├── Makefile
│   └── ...
```


Le processus d'utilisation du Makefile simplifie le déploiement sur différents services cloud en permettant de sélectionner le script de déploiement correspondant au fournisseur choisi.

En premier lieu, le Makefile démarre un conteneur Docker en arrière-plan. Ce conteneur contient les modules nécessaires pour s'authentifier et se connecter aux API des fournisseurs cloud, tels que GCP et Azure. Cette approche garantit que le conteneur reste actif uniquement pendant l'exécution du script Ansible, minimisant ainsi son impact sur le système. Cela contribue également à réduire la durée de vie des variables d'environnement dans le système pendant le déploiement.

Pour utiliser le Makefile, il suffit de se rendre à la racine du fichier services_name correspondant au service cloud désiré. Ensuite, il vous suffit de taper make deploy_${cloud_provider}_${service_name} dans chaque répertoire, où ${cloud_provider} correspond au fournisseur cloud choisi (par exemple, GCP ou Azure) et ${service_name} représente le service spécifique à déployer. Par exemple, pour déployer sur GCP un service de type CaaS a la racine du projet Caas, vous utiliserez la commande make deploy_gcp_caas. De même, pour déployer un exercice sur Azure de type FaaS, vous utiliserez la commande make deploy_azure_exo_faas.

# Diagramme de vie de notre outils make

