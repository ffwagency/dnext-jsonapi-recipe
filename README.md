# Headless - JSON:API

## Overview
The Headless - JSON:API recipe provides a comprehensive setup for creating a headless Drupal application using JSON:API. This recipe includes essential modules and configurations to enable seamless integration with front-end frameworks and applications. It is designed to facilitate the development of decoupled Drupal sites, offering robust API capabilities and efficient content delivery.

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
    "url": "https://github.com/nikolabintev/headless-jsonapi-recipe"
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
composer require nikolabintev/headless-jsonapi-recipe
```

---

## Applying the recipe

Apply the recipe using the following command:
```bash
php web/core/scripts/drupal recipe web/recipes/contrib/seo-recipe

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


Maintainers
Nikola Bintev (GitHub)
