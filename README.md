# Acquia Remote Administration Composer Build Example
[Composer](https://getcomposer.org/) builds allow [Acquia Remote Administration (RA)](https://docs.acquia.com/ra) clients to efficiently include various scripts and patches, including post-update builds.

[Acquia Automation](https://docs.acquia.com/ra/automation) will update Composer built websites whose repositories conform to the proper architecture and include a fully-functioning ```composer.json``` file that builds a Drupal website.

This repository contains sample ```composer.json``` files which can be used to start a working Drupal 8 build. Each example file builds on the previous, with the most comprehensive being ```composer-custom.json```.
* ```composer-basic.json```: This file installs Drupal core, and the required scaffold and installers packages. This is the bare minimum required for a Drupal site on Acquia hosting.
* ```composer-contrib.json```: This file adds a few Drupal contrib modules as well as two modules intended for development only.
* ```composer-libraries.json```:  This file builds on the previous two by illustrating how you can use Composer to add third-party dependencies, like libraries, and install them in specific directories (the example is [drupal/file_browser](https://www.drupal.org/project/file_browser)).
* ```composer-custom.json```: Coming Soon.

Please see [Acquia Automation: Composer builds](https://docs.acquia.com/ra/automation/composer) for a detailed explanation of each section.

## Usage

1. Either use the already present ```composer.json``` file or copy a composer template file into the top level of your repo, renaming it as ```composer.json```.
1. Add the specific Drupal modules, themes and libraries that your site requires. You may do this by manually adding items to the ```require``` section of the ```composer.json``` or running the command ```composer require drupal/modulename```.
1. Ensure that ```drupal-composer/drupal-scaffold``` is required *before* ```drupal/core```.
1. Run ```composer install``` to install all code, vendor directories, etc.

Unless you are using a CI tool, you must commit all generated code to your Acquia repository!

## Resources

* [Composer](https://getcomposer.org/)
* [Acquia Remote Administration](https://docs.acquia.com/ra)
* [Acquia Automation](https://docs.acquia.com/ra/automation)
* [Acquia Automation: Composer builds](https://docs.acquia.com/ra/automation/composer)
