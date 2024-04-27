# Utilisation de Docker et Make pour le déploiement via Ansible sur le Cloud

## Prérequis :
Avant de commencer, assurez-vous d'avoir installé les outils suivants :

### Make :

Sur Windows, vous pouvez installer [Make](https://gnuwin32.sourceforge.net/packages/make.htm) en suivant les instructions disponibles sur le site GNUWin32. Cliquez sur le premier lien et ajoutez les binaires fournis par votre package Make à la variable d'environnement Windows "PATH" pour rendre le binaire disponible dans tous vos interpréteurs de commandes.

Sur Ubuntu/Debian, exécutez la commande suivante dans votre terminal :

```bash
sudo apt update && sudo apt-get install make
```

Sur CentOS/Fedora/Redhat, exécutez la commande suivante dans votre terminal :

```bash
sudo yum update && sudo yum install make
```

### Docker :Suivez les instructions d'installation disponibles sur le site officiel de Docker [(Guide d'installation Docker)](https://docs.docker.com/engine/install).

# Déploiement avec Ansible via Docker et Make :

Une fois que vous avez installé Make et Docker, suivez les étapes ci-dessous pour déployer des instances cloud via Ansible sans avoir à configurer votre PC :

I




