# Drupal-settings

This is the project used for setting up Drupal https://github.com/drupal-composer/drupal-project

Pre-requirements: a local setup with apache, php, mysql and composer (using eg MAMP)

## Step 1

Go to terminal and navigate to where you want to install Drupal locally

## Step 2

Run the composer command replace some-dir for the final directory location. This is going to do all of the folder creations/placements etc

```
composer create-project drupal-composer/drupal-project:9.x-dev some-dir --no-interaction
```

You will probably need to have COMPOSER_MEMORY_LIMIT=-1 added to stop memory crashes. Goal is to upgrade all sites to Composer v2 and this should fix it.

## Step 3

Update Drupal core

```
composer update "drupal/core-*" --with-dependencies
```

## Step 4

Setup the setting.php, setting.local.php and development.services.yml files to

settings.php
settings-local.php
development-service.yml

These will vary slightly depending on who sets them up. Ideally, a standard should be made. My preference is to commit the setting.php file and development.services.yml file to the codebase.

You then locally have the setting.local.php file which can reference the database details and a line to reference the development.service.yml file so that the caches are removed. You can do a similar job on the dev server but reference a different database.

## Step 5

Once the files are set up you can then install a database locally for a default site. You must use MAMP or similar to set up the local hosting of your site first.
