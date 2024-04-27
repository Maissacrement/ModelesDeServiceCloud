# Comment dialogué avec l'api azure par l'intermediaire de clé d'authentification

L'utilisation de l'approche login/password est pratique pour effectuer des tests et attaquer directement le processus de déploiement sur des machines distantes. Cependant, pour un contrôle plus précis et une gestion avancée des services de l'API avec un rôle ayant des actions prédéfinies, par exemple dans le cadre d'une intégration continue (CI), il serait préférable de privilégier le déploiement par souscription d'application sur Azure. Néanmoins, pour notre utilisation actuelle, la connexion par nom d'utilisateur et mot de passe est suffisante.

[Des details concernants les clé necessaire a la souscription par application sont disponible dans ce Readme.md](https://github.com/Maissacrement/azureDeploy)

[En savoir plus sur les roles Azure](https://learn.microsoft.com/fr-fr/azure/role-based-access-control/built-in-roles)
