<p align="center">Projet PHP: Gestion de recette avec Laravel</p>

## Guide d'installation

### 1er étape: Pré-requis

- Installer Laravel. Un guide d'installation se trouve [ici](https://laravel.com/docs/8.x/installation).
- Faire un git clone de ce projet

### 2eme étape: Installation des dépendances et packages nécessaires.
- Installation des dépendances composer avec la commande : `composer install`
- Installation des dépendances npm avec la commande : `npm install`

#### Packages utilisés :
Ces commandes ne sont pas nécessaires pour l'installation.
- Installer le package [https://github.com/laravel/ui](laravel/ui) avec la commande `composer require laravel/ui --dev`
- Installer le package [https://laravelcollective.com/docs](laravelcollective/html) avec la commande `composer require laravelcollective/html` 
- Après l'installation du package précédent, executer cette commande: `php artisan ui bootstrap --auth`

### 3eme étape: Configuration de l'environnement
Dans *config/app.php* rajouter ces éléments si ils n'y sont pas : 

`'providers' => [
....
'Collective\Html\HtmlServiceProvider',
],
'aliases' => [
....
'Form' => 'Collective\Html\FormFacade',
],`
Cela va permettre l'utilisation de *Form* dans nos vues(.blade).

Puis vérifier que dans le fichier *.env* nous avons bien ces informations : 

`DB_CONNECTION=sqlite`
`DB_DATABASE=../database/database.db`

Cela va permettre l'utilisation de la base de donnée *database.db* <br />
<ins>N.B:</ins> Si le fichier **.env** n'existe pas créer celui-ci.

### 4eme étape: Mise en place de la base de donnée

La base de donnée est en principe déjà configurée et prête à être utilisée cependant vous pouvez à tout moment la réinitialiser et la re-populer avec les commandes suivantes: 

`php artisan migrate:fresh`
`php artisan db:seed`

N.B: La population de la base de donnée va permettre la génération de vraies recettes et d'un compte admin avant le remplissage de celle-ci via de fausses informations.


### 5eme étape: Lancement du serveur et identifiant

Une fois toute les étapes précédentes effectuées vous pouvez à présent lancer le serveur local avec la commande : `php artisan serve` <br/>
Il ne vous restera plus qu'à aller sur http://127.0.0.1:8000/ pour visiter le site web. 

Pour vous connecter en tant qu'administrateur il vous suffit de rentrer ces identifiants : 

email : admin@admin.com <br/>
password: adminadmin

Pour vous connecter en utilisateur alpha, vous pouvez créer un utilisateur via le bouton 'register'.

