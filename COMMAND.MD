# SSH alwaysdata

```bash
# UNIX ou LINUX ou GIT BASH
mkdir -p $HOME/.ssh # racine du compte adapter à l'OS
chmod 0700 $HOME/.ssh

# CREER LES CLES SSH
ssh-keygen -t ed25519 -f $HOME/.ssh/id_ed25519

# COPIER LES CLES SSH SUR LE SERVEUR 
ssh-copy-id -i $HOME/.ssh/id_ed25519.pub [user]@ssh-[account].alwaysdata.net

# COPY LE PROJET SF SUR LE SERVEUR UN NOM DE DOMAINE lu07 et un nom d'utilisateur lu07
scp -r projetSF lu07@ssh-lu07.alwaysdata.net:www/public

```
