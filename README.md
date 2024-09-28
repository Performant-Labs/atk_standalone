## Automated Testing Kit Standalone Recipe
Install Automated Testing Kit (ATK) on a Drupal site.

This recipe will:
- Install Automated Testing Kit.
- Set specific contributed module configuration.

## Installation Instructions

- Start with a new Drupal 10.3 (or later) or Drupal 11 site (note that recipes may not work
  on existing sites):
```
composer create-project drupal/recommended-project your_new_site
```
- Add Drush:
```
composer require drush/drush
```
- Install the Standard Drupal profile using the website UI or with:
```
drush site:install --account-name=admin --account-pass=password -y
```
- Allow composer.json to recognize the Github repo with this recipe:
```
  "repositories": [
    {
      "type": "vcs",
      "url": "https://github.com/performant-labs/atk_standalone"
    }
  }
```
- Add the recipe to your site (it will appear in <project_root>/recipes at
  the same level as web):
```
composer require performant-labs/atk_standalone
```
- Apply the recipe.

The recipe can be applied with PHP. Note that `core/scripts/drupal` must be
executable with `chmod +x`.

```shell
cd web
php core/scripts/drupal recipe ../recipes/atk_standalone
```

Clear the cache after the recipe is applied.
