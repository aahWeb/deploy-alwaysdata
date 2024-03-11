# Transférer les données via SSH avec SCP

SCP est la commande nous permetant de transférer des fichiers et dossier.

Pour tranférer des données depuis votre système

```shell
spc chemin_local chemin_serveur
```

si vous voulez transférer des doccier il faut préciser la récursion avec l'option `-r` comme telle :

```shell
scp -r chemin_local chemin_serveur
```