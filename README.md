# TP3 - Terraform - DevSecOps

Dans le cadre de notre TP3, nous avons du déployé une instance de **EC2**, afin de pouvoir déployer et lancer notre programme dessus grâce à **CircleCi** et **Docker**.
Afin d'avoir un environnement reproductible notamment dans le cadre de defaillance sur la **machine virtuel** (notée VM après), et également en cas d'erreurs de configuration trop importantes de pouvoir recommencer facilement.

Pour cela nous avons utilisé un outil d'**Infrastructure As Code**, du nom de **Terraform**. Il nous permet à partir de fichier de configuration de créer une VM selon les spécifications souhaitées. Ici elles seront contrainte car nous voulons utiliser une machine gratuite de AWS.

## Organisation

Voici l'organisation des fichiers :

```
Racine
├── main.tf // Fichier contenant la configuration principale
├── provider.tf // Contient les librairies dont le projet a besoin
└── provider-config.tf // Contient les informations dont AWS a besoin
```
**provider.tf** : Dans ce fichier, il y a la dépendance envers la librairie Terraform qui va permettre de communiquer avec l'API de AWS

**provider-config.tf**: Dans ce fichier, il y a les configurations demandées par AWS pour pouvoir fonctionner

**main.tf** : Dans ce fichier, il y a toutes la configurations de l'instance en elle-même, ainsi que celle du pare-feu réseau et de la clé SSH permettant d'accéder à la machine