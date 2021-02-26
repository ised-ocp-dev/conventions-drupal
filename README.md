# Conventions for Drupal

This tool will check your code against Drupal's coding standard.

It's based on [GrumPHP](https://github.com/phpro/grumphp) and comes with a default configuration tailored for Drupal development.

The following checks are triggered:
* [Drupal coder](https://www.drupal.org/project/coder) code sniffer's checks
* PHPLint
* YAMLlint
* JSONlint
* ESLint

Drupal 7, 8 and 9 are supported.

## Installation

```shell
composer require --dev ised-isde/conventions-drupal
```
### If you're not using GrumPHP

Manually add to your `composer.json` file:
#### Drupal 9
```yaml
    "extra": {
        "grumphp": {
            "config-default-path": "vendor/ised-isde/conventions-drupal/config/drupal9/grumphp.yml"
        }
    }
```

#### Drupal 8
```yaml
    "extra": {
        "grumphp": {
            "config-default-path": "vendor/ised-isde/conventions-drupal/config/drupal8/grumphp.yml"
        }
    }
```
#### Drupal 7
```yaml
    "extra": {
        "grumphp": {
            "config-default-path": "vendor/ised-isde/conventions-drupal/config/drupal7/grumphp.yml"
        }
    }
```

### If you're using GrumPHP already

Edit the file `grumphp.yml.dist` or `grumphp.yml` and add on the top it:

#### Drupal 8
```yaml
imports:
  - { resource: vendor/ised-isde/conventions-drupal/config/drupal8/grumphp.yml }
```
#### Drupal 7
```yaml
imports:
  - { resource: vendor/ised-isde/conventions-drupal/config/drupal7/grumphp.yml }
```

To add an extra Grumphp task:

```yaml
imports:
  - { resource: vendor/ised-isde/conventions-drupal/config/drupal7/grumphp.yml }

parameters:
  extra_tasks:
    phpunit:
      always_execute: false
```

In conjunction with `extra_tasks`, use `skip_tasks` to skip tasks if needed.
