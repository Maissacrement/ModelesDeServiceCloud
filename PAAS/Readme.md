# Deploiement Plateforme as a Service (IAAS)

GKE et AKS sont des services phares de Google Cloud et Microsoft Azure respectivement, offrant une solution PaaS complète pour le déploiement et la gestion d'applications conteneurisées. Ces services permettent aux développeurs de se concentrer entièrement sur le développement et l'innovation, en déchargeant les préoccupations liées à la gestion de l'infrastructure sous-jacente.

Avec GKE et AKS, Google Cloud et Microsoft Azure simplifient considérablement le déploiement et l'orchestration des conteneurs, en fournissant une plateforme robuste et hautement disponible pour exécuter des applications basées sur Kubernetes. Ces services prennent en charge l'automatisation des mises à jour, la mise à l'échelle automatique et la surveillance avancée, offrant ainsi une expérience sans souci pour les développeurs.

# Source

C'est le code où l'application de type IaaS est compilée. L'image du conteneur est gérée par un Makefile, ce qui permet d'automatiser et de rendre plus fiable la création de votre artefact. Vous pouvez après avoir jeter un coup d'oeil, acceder à l'image docker: [maissacrement/azure-functionapp](https://hub.docker.com/repository/docker/maissacrement/ansibledind/general)

[Voir le depot git](https://github.com/Maissacrement/azureDeploy)

# Comment deployer

[Cours sur comment fonctionne le makefile](../cours/10.DeployInstruction.md). Toute les commande devrons etre executer depuis le repertoire IAAS ou se trouve le Makefile.

## GCP

Si vous faite l'exercice, et que vous modifié le fichier `deploy_exo.yml` dans repertoire `gcp`. Vous devrez a partir du dossier iaas, tapez:

```bash
make deploy_gcp_exo_iaas
```

Si vous souhaitez uniquement voir et executez le corrigé `deploy.yml` dans le repertoire `gcp`, vous devrez taper:

```bash
make deploy_gcp_iaas
```

## AZURE

Si vous faite l'exercice, et que vous modifié le fichier `deploy_exo.yml` dans repertoire `azure`. Vous devrez a partir du dossier iaas, tapez:

```bash
make deploy_azure_exo_iaas
```

Si vous souhaitez uniquement voir et executez le corrigé `deploy.yml` dans le repertoire `azure`, vous devrez taper:

```bash
make deploy_azure_iaas
```