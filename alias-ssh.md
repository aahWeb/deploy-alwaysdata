# Les Alias SSH

## Introduction

Les alias SSH sont des raccourcis pratiques qui permettent aux utilisateurs d'effectuer des connexions SSH à des hôtes distants en utilisant des noms conviviaux au lieu d'adresses IP ou de noms de domaine complets. Cela simplifie grandement le processus de connexion à des serveurs distants et peut améliorer l'efficacité des tâches administratives.

## Création d'Alias SSH

Pour créer un alias SSH, nous devons éditer le fichier `~/.ssh/config` sur notre machine locale. Ce fichier contient des configurations pour les connexions SSH, y compris les alias.

Voici un exemple de syntaxe pour définir un alias SSH dans `~/.ssh/config` :

```plaintext
Host mon_alias
    HostName adresse_ip_ou_domaine
    User utilisateur
    Port port_ssh
```

- `mon_alias` : Le nom convivial que nous voulons utiliser pour notre alias SSH.
- `adresse_ip_ou_domaine` : L'adresse IP ou le nom de domaine de l'hôte distant.
- `utilisateur` : Le nom d'utilisateur que nous utilisons pour nous connecter à l'hôte distant.
- `port_ssh` : Le numéro de port SSH sur lequel le serveur distant écoute les connexions SSH. Ce paramètre est facultatif et peut être omis s'il utilise le port par défaut (22).

## Exemples

### Exemple 1 : Connexion à un serveur distant avec un alias SSH

Supposons que nous voulions nous connecter à un serveur distant avec l'adresse IP `192.168.1.100`, en utilisant l'utilisateur `admin` et le port SSH par défaut.

Nous pouvons définir un alias SSH nommé `mon_serveur` dans notre fichier `~/.ssh/config` comme ceci :

```plaintext
Host mon_serveur
    HostName 192.168.1.100
    User admin
```

Maintenant, pour nous connecter à ce serveur distant, nous pouvons simplement exécuter la commande suivante dans notre terminal :

```bash
ssh mon_serveur
```

### Exemple 2 : Connexion à un serveur distant avec un port SSH personnalisé

Si le serveur distant écoute sur un port SSH personnalisé, par exemple le port `2222`, nous pouvons spécifier le port dans notre alias SSH comme suit :

```plaintext
Host mon_serveur
    HostName 192.168.1.100
    User admin
    Port 2222
```

Nous pouvons ensuite nous connecter au serveur distant en utilisant la même commande SSH :

```bash
ssh mon_serveur
```

### Exemple 3 : Utilisation d'options avancées dans un alias SSH

Voici un exemple d'alias SSH qui inclut des options avancées dans le fichier de configuration `~/.ssh/config` :

```plaintext
Host alwaysdata
    IgnoreUnknown AddKeysToAgent
    IgnoreUnknown UseKeychain
    HostName ssh-mcstn.alwaysdata.net
    User mcstn
    IdentitiesOnly yes
    IdentityFile ~/.ssh/alwaysdata
    AddKeysToAgent yes
    UseKeychain yes
```

Dans cet exemple :
- `IgnoreUnknown AddKeysToAgent` et `IgnoreUnknown UseKeychain` sont des options qui indiquent à SSH d'ignorer les paramètres inconnus s'ils se produisent dans le fichier de configuration.
- `HostName` spécifie l'adresse du serveur distant.
- `User` spécifie le nom d'utilisateur utilisé pour se connecter au serveur.
- `IdentitiesOnly yes` indique à SSH d'utiliser uniquement les clés privées spécifiées dans `IdentityFile`.
- `IdentityFile` spécifie le chemin de la clé privée utilisée pour l'authentification.
- `AddKeysToAgent yes` et `UseKeychain yes` ajoutent la clé privée à l'agent SSH et utilisent le trousseau d'accès respectivement.

## Conclusion

Les alias SSH sont un outil précieux pour simplifier les connexions SSH à des hôtes distants. En définissant des alias dans le fichier de configuration SSH, les utilisateurs peuvent se connecter à des serveurs distants en utilisant des noms conviviaux au lieu de devoir se souvenir des adresses IP et des noms d'utilisateur complets. Cela peut grandement améliorer l'efficacité et la facilité d'utilisation lors de l'administration des systèmes distants.