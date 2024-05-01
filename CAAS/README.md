# Deployer un service de type Container as a service CAAS

Déploiement des Container as a Service vers le cloud

# Nginx

Le repertoire nginx n'est pas à configurer sauf si vous souhaitez deployer une image personnalisé.

# Source

C'est le code où l'application de type CaaS est compilée. L'image du conteneur est gérée par un Makefile, ce qui permet d'automatiser et de rendre plus fiable la création de votre artefact. Vous pouvez après avoir jeter un coup d'oeil, acceder à l'image docker: [maissacrement/azure-functionapp](https://hub.docker.com/repository/docker/maissacrement/ansibledind/general)

[Voir le depot git](https://github.com/Maissacrement/azureDeploy)

# Comment deployer

[Cours sur comment fonctionne le makefile](../cours/10.DeployInstruction.md). Toute les commande devrons etre executer depuis le repertoire CaaS ou se trouve le Makefile.

## GCP

Si vous faite l'exercice, et que vous modifié le fichier `deploy_exo.yml` dans repertoire `gcp`. Vous devrez a partir du dossier CaaS, tapez:

```bash
make deploy_gcp_exo_caas
```

Si vous souhaitez uniquement voir et executez le corrigé `deploy.yml` dans le repertoire `gcp`, vous devrez taper:

```bash
make deploy_gcp_caas
```

## AZURE

Si vous faite l'exercice, et que vous modifié le fichier `deploy_exo.yml` dans repertoire `azure`. Vous devrez a partir du dossier caas, tapez:

```bash
make deploy_azure_exo_caas
```

Si vous souhaitez uniquement voir et executez le corrigé `deploy.yml` dans le repertoire `azure`, vous devrez taper:

```bash
make deploy_azure_caas
```
