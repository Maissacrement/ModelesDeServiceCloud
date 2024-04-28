# Cloud Supdevinci bachelor 3 2024

## Infrastructure

[Redhat](https://www.redhat.com/en/topics/cloud-computing/what-is-it-infrastructure): Les infrastructures de technologie de l'information (IT) sont les composants nécessaires pour faire fonctionner et gérer environnements IT d'entreprise. 

Il sont generalement decris sous forme de schema appellé aussi diagramme.  Les schémas ou diagrammes des infrastructures informatiques permettent de visualiser la disposition des composants matériels et logiciels, ainsi que leurs interconnexions. Cette représentation visuelle est cruciale pour comprendre la structure et le fonctionnement de l'infrastructure, facilitant ainsi la planification, la gestion et la prise de décision. En effet, en observant un tel diagramme, les professionnels de l'IT peuvent rapidement identifier les points de congestion, les éventuels goulets d'étranglement et les zones de vulnérabilité, ce qui leur permet de mettre en œuvre des solutions adaptées pour optimiser les performances et renforcer la sécurité du système.
[La suite dans le cours](./Cours/5.ITInfrastructure.md)

Exemple: Ce schéma représente une connexion VPN classique entre votre réseau d'entreprise et le service cloud. Il met en évidence la liaison sécurisée établie par les tunnels VPN IPsec entre les hôtes sur site et les instances de machines virtuelles dans le cloud. Cette infrastructure assure une connectivité fiable et chiffrée, permettant un accès sécurisé aux ressources cloud depuis le réseau local de l'entreprise. [En savoir plus](https://cloud.google.com/network-connectivity/docs/vpn/concepts/classic-topologies?hl=fr)

<img style="max-height:400px" src="./assets/infra-cloud.png">

## Transition vers l'Infrastructure as Code (IaC)

La transition vers l'Infrastructure as Code (IaC) représente une évolution logique dans la gestion des infrastructures informatiques. Avant cette approche, la gestion des ressources était souvent sujette à des processus manuels propices aux erreurs et aux retards. Avec l'IaC, les ressources système sont représentées sous forme de code, offrant ainsi une automatisation et une reproductibilité accrues.

L'un des avantages majeurs de l'IaC est la possibilité de versionner l'infrastructure, facilitant ainsi la collaboration entre les intervenants et permettant de suivre en temps réel l'évolution du système. L'utilisation d'outils de versionnement comme Git devient alors indispensable pour garantir la cohérence et la fiabilité de l'infrastructure.

Dans cette transition, il est crucial de ne pas se fier à une image mentale de l'infrastructure. Cette approche est sujette à des erreurs de mémoire et à des interprétations subjectives. En revanche, un script Ansible représentant la configuration des ressources offre une alternative concrète et reproductible. Il contient des données précises et exploitables, favorisant ainsi une gestion plus précise et fiable des ressources. [La suite dans le cours](./Cours/6.IaC.md)

Illustrons cette différence par deux exemples: une configuration manuelle de ressources versus un script Ansible représentant la même configuration. Bien que les données semblent similaires, il est clair que l'un est une simple image non exploitable tandis que l'autre est un script personnalisable et reproductible. En adoptant l'Infrastructure as Code, les organisations peuvent atténuer les risques d'erreurs et rationaliser leurs opérations grâce à une approche plus fiable et automatisée de la gestion de l'infrastructure. 


<img style="width:70%;position:relative;float:left" src="./assets/storage_account.png" /><img style="width:30%;position:relative;float:left" src="./assets/ansible-storage-account.png" />

<br/>
<br style="clear:both"/>


## Cloud Privé vs Cloud Public

Lorsque vous explorez les options de cloud computing, il est important de connaître les différentes possibilités qui s'offrent à vous. Si vous souhaitez avoir un contrôle total sur votre infrastructure cloud, des solutions comme [OpenStack](https://docs.openstack.org/2024.1/install/) permettent de déployer votre propre cloud privé. Cependant, cela signifie que vous devrez assumer la responsabilité du provisionnement manuel des ressources lorsque votre infrastructure atteint ses limites physiques. Il est crucial d'anticiper cette situation pour éviter tout impact sur les processus en cours, comme les temps d'attente pour les processus de construction et la perte d'artefacts. La gestion manuelle des ressources offre une flexibilité accrue, mais nécessite une surveillance et une planification constantes pour maintenir des performances optimales. L'intégration d'outils tels que [Node Exporter](https://github.com/grafana/grafana), [Grafana](https://github.com/prometheus/node_exporter), [AlertManager](https://github.com/prometheus/alertmanager) et [Prometheus](https://github.com/prometheus/node_exporter) permet d'ajouter un système de monitoring et d'alerting à votre infrastructure, ce qui vous permet d'anticiper les besoins en ressources de votre cloud privé.

<img src="./assets/public-private-cloud.avif">

L'externalisation de l'infrastructure informatique vers le cloud présente de nombreux avantages pour les entreprises, notamment :

Réduction des coûts: Le cloud computing offre une flexibilité et une évolutivité significatives, permettant aux entreprises de réduire les investissements initiaux, d'optimiser les dépenses opérationnelles et d'éliminer les frais de maintenance. De plus, grâce à la nature virtuelle du cloud, les entreprises peuvent s'installer numériquement dans n'importe quelle [régions](./Cours/5.Regions.md) sans avoir à y investir physiquement. Cependant, chaque entreprise doit évaluer attentivement ses besoins spécifiques en infrastructure pour choisir la solution qui lui convient le mieux en termes de coûts, de performances et de contrôle.

Flexibilité et évolutivité: Le cloud permet une adaptabilité rapide aux changements d'activité, facilitant l'augmentation ou la réduction des ressources en fonction des besoins fluctuants. Cela évite les problèmes de sous-dimensionnement ou de surdimensionnement en assurant un accès à la juste quantité de ressources au bon moment. De plus, la gestion des pics d'activité est simplifiée, permettant une anticipation et une gestion aisée des périodes de forte demande.

Accessibilité et disponibilité: Les services cloud offrent un accès aux données et aux applications depuis n'importe où, favorisant le travail à distance, la collaboration facilitée et une meilleure productivité. De plus, les infrastructures cloud redondantes garantissent une disponibilité 24/7 et réduisent les risques de pannes et de perte de données, offrant ainsi une continuité de service optimale.

Innovation et expertise: En optant pour le cloud, les entreprises peuvent accéder aux dernières technologies et bénéficier des mises à jour constantes pour rester à la pointe du progrès. De plus, en déléguant l'infrastructure informatique à des spécialistes du cloud, elles peuvent se concentrer sur leurs activités stratégiques tout en profitant de l'expertise des fournisseurs cloud pour optimiser leur utilisation du cloud.

## Services Cloud (IaaS, PaaS, SaaS, CaaS et FaaS) dans GCP et Azure

Le cloud computing offre une multitude de modèles de service pour répondre aux besoins variés des utilisateurs, chacun proposant un niveau d'abstraction et de gestion des ressources distinct. Explorons ces modèles et leur déclinaison dans les plateformes cloud majeures, Google Cloud Platform (GCP) et Microsoft Azure. [La suite dans le cours](./Cours/4.ServicesCloud.md)

<img src="./assets/modeles-de-services-cloud.png">


## Ansible


Ansible simplifie la gestion des opérations côté administrateur système en automatisant le déploiement, la configuration et la maintenance de l'infrastructure, ce qui permet d'améliorer l'efficacité et la cohérence des opérations.
Utilisé les modules [azure](https://docs.ansible.com/ansible/latest/collections/azure/azcollection/index.html) et [gcp](https://docs.ansible.com/ansible/latest/collections/google/cloud/index.html) et n'hesitez pas a utilisé la cli via le module 'shell' ansible des providers cloud [gcp](https://cloud.google.com/sdk/docs/scripting-gcloud?hl=fr) at [azure](https://learn.microsoft.com/fr-fr/cli/azure/reference-index?view=azure-cli-latest) pour des besoin plus fin.

### Comment deployer vos script Ansible ?

`Docker` et `Make` sont les seuls dependance necessaire sur votre systeme ! [Voir les pre-requis et les spécificités concernant le fichier Makefile et comment l'utiliser.](./Cours/10.DeployInstruction.md)

Le Makefile disponible à la racine de chaque projet permet l'utilisation facile de la cli de votre provider cloud (az cli ou gcloud) et des modules Ansible sans nécessiter de téléchargement supplémentaire. Tout est pré-embarqué dans un conteneur Docker, simplifiant ainsi le déploiement des services cloud sans aucune manipulation supplémentaire de la part de l'utilisateur final.

```bash
Service proposé par les providers cloud gcp et azure
CLOUD_PROVIDERS_SERVICES
├── README.md
├── services_name
│   ├── gcp
|   │   ├── deploy.yml # Votre script de deploiement
|   │   ├── .env.exemple # Vos secret
|   │   ├── .env # N'existe pas! Copiez le .env.exemple
|   │   ├── account # N'existe pas! Uploader votre json
|   |   │   ├── my-account.json # Complement de secrets
|   ├── azure
|   │   ├── deploy.yml
|   │   ├── .env # Vos secret
│   ├── Makefile # L'executeur
│   └── ...
```
Methodologie de travail et de deploiement en local depuis votre pc en utilisant ce Makefile. Afin de savoir comment deployé avec le Makefile [Voir le cours](./Cours/10.DeployInstruction.md)

[En savoir plus sur le container de deploiement](https://github.com/Maissacrement/azureDeploy)

## Approfondissez vos connaissances avec des cours en ligne et des vidéos.

```yaml
Openstack:
- Description: 'Hebergé votre propre Cloud'
- Presentation: 'https://www.youtube.com/watch?v=BmwgKF5Jc0g'
- Documention: 'https://docs.openstack.org/2024.1/install/'
- Infrastructure:
    Tacker:
        description: 'Tacker est un outil dans OpenStack qui permet de déployer et de gérer des services réseau et des fonctions de réseau virtuel (VNF) de manière automatisée sur une infrastructure de virtualisation des fonctions réseau (NFV). Il utilise un cadre standard appelé ETSI MANO pour orchestrer ces services et fonctions, offrant ainsi une solution complète pour la gestion des réseaux virtuels.'
        diagramme: 'https://wiki.openstack.org/wiki/Tacker'
    Baremetal:
        description: 'Le service Bare Metal, nom de code ironic, est une collection de composants cela fournit un support pour gérer et provisionner des machines physiques.'
        diagramme: 'https://docs.openstack.org/ironic/2024.1/install/get_started.html' 
```
# Plus et decouvertes

Ansible deployé des docker-compose file
https://github.com/Maissacrement/cloudprovision/blob/main/playbook.yml

Adoptez une approche Infrastructure as Code pour générer des machines virtuelles exportables sur n'importe quelle machine, éliminant ainsi l'échange de snapshots
https://github.com/Maissacrement/FreeBSDAnsible/blob/master/Vagrantfile

## Comment mettre a jour votre fork github

[how_to_sync_your_fork](https://stackoverflow.com/questions/7244321/how-do-i-update-or-sync-a-forked-repository-on-github)
