# Sur votre serveur alwaysdata via SSH

Vous voilà maintenant dans la "matris" (non on n'est pas dans Matrix, mais dans un serveur web).

> [!TIP]
> Pour connaitre la distribution Linux, vous pouvez exécuter la commande `uname -a`.

Plusieurs outilles sont à notre disposition. Si vous voulez savoir si une commande est disponible, vous pouvez utiliser la commande `which commande-rechercher` qui vous indique le chemin binaire de la commande (variable d'environnement). Si vous avez un chemin qui vous es retourné, alors, la commande est disponible.

# Trouver composer

Lancez la commande `which composer`. On retrouve bien notre gestionnaire de dépendance, mais si on jette un oeil à sa version avec `composer --version`, on remarque qu'elle est ultérieure : 1.10.x

Pour utiliser une version plus récente, vous devez utiliser la commande `composer2`. Je vous invite à vérifier par vous-même la version de cette commande.