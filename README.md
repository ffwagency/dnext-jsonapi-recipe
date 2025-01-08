# DNext - JSON:API

## Overview
The DNext - JSON:API recipe provides a comprehensive setup for creating a decoupled Drupal application using JSON:API and Next.js. This recipe includes essential modules and configurations to enable seamless integration between Drupal and Next.js. It is designed to facilitate the development of modern, performant websites by combining Drupal's powerful content management capabilities with Next.js's server-side rendering and static site generation features.

## Prerequisites
Ensure your Drupal installation is configured to apply recipes by following the instructions:
- [Drupal 10](https://git.drupalcode.org/project/distributions_recipes/-/blob/1.0.x/docs/getting_started.md)
- [Drupal 11](https://git.drupalcode.org/project/distributions_recipes/-/blob/1.0.x/docs/getting_started_d11.md)

## Installation

### Ignore the contributed recipes directory
Add the following line to the project's `.gitignore` file:

```txt
# Ignore contributed recipes
web/recipes/contrib
```

### Configure composer.json
- Update the `repositories` section of the project's composer.json, so it includes a reference to this repository.
```json
"repositories": [
  {
    "type": "vcs",
    "url": "git@github.com:ffwagency/dnext-jsonapi-recipe.git"
  }
]
```
- Configure the installer paths in the `extra` section of the project's composer.json.

```json
{
    "extra": {
        "installer-paths": {
            "web/recipes/contrib/{$name}": [
              "type:drupal-recipe"
            ]
        }
    }
}
```

### Require the package
Require the package using composer.
```bash
composer require ffwagency/dnext-jsonapi-recipe
```

---

## Applying the recipe

### Cache rebuild
Before applying the recipe, ensure the cache is rebuilt, so the module and theme extensions are updated with
the newly installed ones from the recipe.

```bash
drush cr
```

### Apply

<strong>Important!</strong> The recipe must be applied within the Drupal container from Drupal's project root directory.
```bash
cd {PROJECT_ROOT}
php core/scripts/drupal recipe recipes/contrib/dnext-jsonapi-recipe
```
---
## Features
### JSON:API
The JSON:API module provides a standards-compliant API for accessing and manipulating Drupal content.

### JSON:API Extras
The JSON:API Extras module allows customization of the JSON:API output, including renaming resource types and fields.

### JSON:API Image Styles
The JSON:API Image Styles module exposes image styles through the JSON:API.

The recipe defines a single image style called `webp` that converts images to the WebP format.
### JSON:API Menu Items
The JSON:API Menu Items module provides access to menu items via the JSON:API.

### JSON:API Resources
The JSON:API Resources module allows the creation of custom JSON:API resources.

### JSON:API Schema
The JSON:API Schema module provides a JSON Schema for the JSON:API output.

### Next.js Integration
The Next.js module facilitates integration with the Next.js framework, enabling server-side rendering and static site generation.

## Patches

The list of patches defined in the [patches.json](patches.json) file should be applied to the project root composer.json file.