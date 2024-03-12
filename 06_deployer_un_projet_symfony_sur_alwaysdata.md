# Déployer son projet Symfony sur Alwaysdata

# Préparer son projet

On peut omettre l'envoi de certains dossiers puisque dans le développement de notre application, certaines dépendances sont des "dépendances de développement" qui n'ont donc pas lieu d'être dans l'application en production.

Les dossiers à envelver pour le déploiement :
- vendor/
- var/

Ces fichiers seront regénérés lors de l'exécution de la commande `composer2 install --no-dev --optimize-autoloader` sur le serveur.

## Configurer l'Environnement de Production

Avant de déployer votre application, assurez-vous que l'environnement de production est correctement configuré. Cela inclut :

- **Paramètres d'environnement**: Configurez les variables d'environnement nécessaires à votre application dans Alwaysdata. Cela peut inclure des variables pour la base de données, les clés API, etc.

- **PHP et Extensions**: Vérifiez que la version PHP utilisée est compatible avec votre version de Symfony. Assurez-vous également que toutes les extensions PHP requises par votre application sont installées et activées.

## Déployer son projet

1. **Envoyer les fichiers sur le serveur**:
   - Utilisez FTP/SFTP, SCP ou Git (si supporté par votre hébergeur) pour transférer les fichiers de votre projet à l'exception des dossiers `vendor/` et `var/` sur votre espace d'hébergement Alwaysdata.
   
2. **Configuration du serveur web**:
   - Configurez votre serveur web pour pointer vers le dossier `public/` de votre application Symfony. Ceci est crucial pour la sécurité et le bon fonctionnement de votre application.

3. **Installation des dépendances**:
   - Connectez-vous à votre serveur via SSH.
   - Naviguez jusqu'au dossier racine de votre projet.
   - Exécutez `composer2 install --no-dev --optimize-autoloader` pour installer les dépendances de production tout en optimisant l'autoloader de Composer.

4. **Configuration de l'environnement**:
   - Assurez-vous que la variable d'environnement `APP_ENV` est définie sur `prod` pour indiquer que votre application fonctionne en environnement de production.

5. **Vider le cache**:
   - Exécutez `php bin/console cache:clear --no-warmup --env=prod` pour vider le cache. Vous pouvez ensuite réchauffer le cache avec `php bin/console cache:warmup --env=prod` si nécessaire.

6. **Configurer la base de données** (si pas déjà fait) :
   - Exécutez `php bin/console doctrine:migrations:migrate` pour appliquer les migrations à votre base de données en production.

## Ressources à consulter sans modération

- **Documentation Symfony sur le déploiement**: Continuer à se référer à la documentation officielle de Symfony pour le déploiement pour des conseils approfondis et des pratiques recommandées :  
    https://symfony.com/doc/current/deployment.html

- **Documentation Alwaysdata**: Consultez également la documentation d'Alwaysdata pour des instructions spécifiques à leur plateforme, notamment sur la configuration des serveurs web, la gestion des bases de données, et les paramètres PHP:  
    https://help.alwaysdata.com/fr/

En suivant ces étapes et en consultant les ressources recommandées, vous serez bien équipé pour déployer efficacement votre projet Symfony sur Alwaysdata. N'oubliez pas de tester soigneusement votre application en production pour vous assurer que tout fonctionne comme prévu.

Bien sûr, je vous encourage à faire des recherches complémentaires pour le déploiement de votre projet.