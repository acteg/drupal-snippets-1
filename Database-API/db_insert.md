# DB Insert

[db_insert sur drupal.org](https://www.drupal.org/node/310079)

## Requète simple d'insertion dans la table node
```php
$nid = db_insert('node') ->fields(array(
  'title' => 'Example',
  'uid' => 1,
  'created' => REQUEST_TIME,
))->execute();
```
