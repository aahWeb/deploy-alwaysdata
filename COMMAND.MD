# SSH alwaysdata

```bash
# UNIX ou LINUX ou GIT BASH
mkdir -p $HOME/.ssh # racine du compte adapter à l'OS
chmod 0700 $HOME/.ssh

# CREER LES CLES SSH
ssh-keygen -t ed25519 -C "ssh-lu07.alwaysdata.net" -f $HOME/.ssh/id_ed25519

# COPIER LES CLES SSH SUR LE SERVEUR 
ssh-copy-id -i $HOME/.ssh/id_ed25519.pub [user]@ssh-[account].alwaysdata.net

# COPY LE PROJET SF SUR LE SERVEUR UN NOM DE DOMAINE lu07 et un nom d'utilisateur lu07
scp -r projetSF lu07@ssh-lu07.alwaysdata.net:www/public
```

Sur Windows, les commandes `ssh` et `ssh-keygen` exists, à l'exception de `ssh-copy-id`, ce qui vous demandera d'inscrire la clé publique manuellement dans le serveur, dans le fichier `~/.ssh/authorized_keys` et de définir ces permissions avec la commande `chmod 600 ~/.ssh/authorized_keys`. Vous pouvez aussi passer par **bash** si vous avez installé [WSL (Windows Sub-System for Linux)](https://www.notion.so/mathieu-constantin/Shell-Linux-sur-Windows-WSL-8dd6fe29b28f4acf899140e5f24c3169?pvs=4).