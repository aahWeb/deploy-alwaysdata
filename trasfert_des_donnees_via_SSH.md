# Transférer les données via SSH avec SCP

`scp` est la commande nous permettant de transférer des fichiers et dossiers de manière sécurisée.

**SCP** sont les acronymes de **Secur CoPy**.

# Théoriquement comment fonctionne SCP ?

Pour transférer des données d'un système à un autre, il vous faudra renseigner **en premier l'hôte expéditeur** avec le chemin pointant la ressource à expédier et **en dernier l'hôte destinataire** avec le chemin pointant le répertoire où sera receptionnée la ressource.

```shell
scp hote:chemin_systeme_1 nom_utilisateur@[hote]:chemin_systeme_2/
```

si vous voulez transférer des dossiers il faut préciser la **récursion** avec l'option `-r` comme telle :

```shell
scp -r hote:chemin_systeme_1 nom_utilisateur@[hote]:chemin_systeme_2/
```

# Concrétement comment fonctionne SCP pour nous ?

Si on fait attention, on comprend qu'il y a un hôte qui correspond à notre système local... Pas besoin de l'indiquer. Donc si on expédie une donnée, ça nous donne cette commande :

```shell
scp chemin/donnée/ utilisateur@server.com:chemin/dossier
```

Dans mon cas, je veux envoyer le dossier projet_x dans le dossier www se trouvant sur mon serveur Alwaysdata. Voici à quoi ressemble ma commande :

```shell
scp -r ./projet_x mcstn@ssh-mcstn.alwaysdata.net:www/
```

Je peux fair encore plus fort si c'est le contenu du dossier `projet_x/` que je veux transférer dans `www/` :


```shell
scp -r ./projet_x/* mcstn@ssh-mcstn.alwaysdata.net:www/
```

> [!TIP]
> Pour préciser le port du serveur c'est le flag `-P` qu'il faut indiquer et non `-p`, ce second flag indique qu'on garde les métadonnées des fichiers tel que la date de création, la dernière date de modification, etc...