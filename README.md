## ATK Standalone Recipe
Create a standalone Drupal site with Automated Testing Kit (ATK) for demonstration purposes
or when starting a new project that will use ATK.

This recipe is designed to:
- Add Automated Testing Kit.
- Set specific contributed module configuration.

## Installation Instructions

- Start with a new Drupal 10 site (recipes may not work on existing sites):
```
composer create-project drupal/recommended-project your_new_site
```
- Install the 'Standard' profile using the website UI.
- Allow composer.json to recognize recipes:
```  
  "installer-types": ["drupal-recipe"],
  "installer-paths": {
     // Existing entries are here.
     "web/recipes/contrib/{$name}": [
       "type:drupal-recipe"
     ]
  }
```
- Add the patch to composer.json so that Drupal can work with recipes:
```
  "patches": {
    "drupal/core": {
      "Allow recipes to be applied":"https://git.drupalcode.org/project/distributions_recipes/-/raw/patch/recipe.patch"
    }
  }
```
- Allow composer.json to recognize the Github repo with the recipe:
```
  "repositories": [
    {
      "type": "vcs",
      "url": "https://github.com/perfomant-labs/atk_standalone"
    }
  }
```
- Add the recipe to your site:
```
composer require performant-labs/atk_standalone
```
- Update dependencies:
```
composer update
```

- Apply the recipe.

The recipe can be applied with PHP. Note that `core/scripts/drupal` must be
executable with `chmod +x`.

```shell
php core/scripts/drupal recipe recipes/contrib/atk_standalone
```

Clear the cache after the recipe is applied. When going back to the site,
all the recipe configuration and customization has been applied.
