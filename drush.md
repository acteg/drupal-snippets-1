#Drush

## Installation / Upgrade / Downgrade
|**commande**|**Résultat**|
|------------|------------|
|`composer global require drush/drush:6.5`|repasser à la version 6.5 stable|
|`composer global require drush/drush:6.*`|passer sur la dernière version stable de la branche 6.x|
|`composer global require drush/drush:7.*`|passer sur la dernière version stable de la branche 7.x|
|`composer global require drush/drush:8.*`|passer sur la dernière version stable de la branche 8.x|
|`composer global require drush/drush:dev-master`|passer sur la version dev|
|`composer global update drush/drush`|mettre à jour drush|

## Autopsie d'un Alias
Se trouvent dans le fichier ~/.drush/alias.drush.php
```php
$aliases['monsite'] = array( //Nom de l'alias
  'uri' => 'monsite.dev', //url
  'root' => '/media/vhosts/monsite.dev/www/', // chemin d'accès à l'instance du drupal
);
```

## Fonctions générales
|**commande**|**Résultat**|
|------------|------------|
|`Drush use @alias`|rentre dans le namespace @alias, ainsi les commandes suivantes n'auront pas besoin de spécifier d'alias|

##Installation de drupal
|Commande|Résultat|
|--------|--------|
|`drush dl drupal-8.x --select --drupal-project-rename=www`|Propose les différentes versions de D8 disponibles, puis télécharge la version choisie et la place dans un dossier **www**|

## Gestion de module
|**commande**|**Alias**|**Résultat**|
|------------|------------|------------|
|`drush pm-download projet`|`dl`|Télécharge le module **projet**|
|`drush pm-enable projet`|`en`|Active le module **projet**|
|`drush pm-releasenotes projet`|`rln`|Affiche le changelog pour le module **projet**|
|`drush pm-update projet`|`up`|Met à jour le module **projet**|
|`drush pm-update`|`up`|Met à jour l'ensemble des modules|
|`drush pm-updatestatus`|`ups`|Affiche la liste des mises à jours disponibles pour les projets activées|

##Search API
|Commande|Résultat|
|--------|--------|
|`drush @alias sapi-s`|Affiche le statut des index de recherche|
|`drush @alias sapi-c`|Vide les indexes de recherche|
|`drush @alias sapi-i`|Lance une réindexation pour l'ensemble des indexes|
|`drush @alias sapi-r`|Marque les indexes pour réindexation|
