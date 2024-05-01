# DEPLOYER une Function as a Service (FaaS)

Déploiement des Fonction as a Service vers le cloud

# Source

C'est le code où l'application de type FaaS est compilée. L'image du conteneur est gérée par un Makefile, ce qui permet d'automatiser et de rendre plus fiable la création de votre artefact. Vous pouvez après avoir jeter un coup d'oeil, acceder à l'image docker: [maissacrement/azure-functionapp](https://hub.docker.com/repository/docker/maissacrement/ansibledind/general)

[Voir le depot git](https://github.com/Maissacrement/azureDeploy)

# Comment deployer

[Cours sur comment fonctionne le makefile](../cours/10.DeployInstruction.md). Toute les commande devrons etre executer depuis le repertoire FAAS ou se trouve le Makefile.

## GCP

Si vous faite l'exercice, et que vous modifié le fichier `deploy_exo.yml` dans repertoire `gcp`. Vous devrez a partir du dossier FAAS, tapez:

```bash
make deploy_gcp_exo_faas
```

Si vous souhaitez uniquement voir et executez le corrigé `deploy.yml` dans le repertoire `gcp`, vous devrez taper:

```bash
make deploy_gcp_faas
```

## AZURE

Si vous faite l'exercice, et que vous modifié le fichier `deploy_exo.yml` dans repertoire `azure`. Vous devrez a partir du dossier FAAS, tapez:

```bash
make deploy_azure_exo_faas
```

Si vous souhaitez uniquement voir et executez le corrigé `deploy.yml` dans le repertoire `azure`, vous devrez taper:

```bash
make deploy_azure_faas
```