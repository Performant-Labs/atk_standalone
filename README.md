## ATK Standalone Recipe
Create a standalone Drupal site with Automated Testing Kit (ATK) for demonstration purposes
or when starting a new project that will use ATK.

This recipe is designed to do the following:

- Install Drupal - Standard version.
- Add Automated Testing Kit and some useful modules.
- Set specific contributed module configuration.

## Installing

- Start with a Drupal 10 site.
- Install the 'Standard' profile.
- Apply the recipe.

The recipe can be applied with PHP. Note that `core/scripts/drupal` must be
executable with `chmod +x`.

```shell
php core/scripts/drupal recipe recipes/contrib/atk_standalone
```

Clear the cache after the recipe is applied. When going back to the site,
all the recipe configuration and customization has been applied.
