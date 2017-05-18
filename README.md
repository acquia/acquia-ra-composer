# Acquia Remote Administration Composer Build Example
[Composer](https://getcomposer.org/) builds allow [Acquia Remote Administration (RA)](https://docs.acquia.com/ra) clients to efficiently include various scripts and patches, including post-update builds.

[Acquia Automation](https://docs.acquia.com/ra/automation) will update Composer built websites whose repositories conform to the proper architecture and include a fully-functioning ```composer.json``` file that builds a Drupal website.

This repository contains sample ```composer.json``` files which can be used to start a working Drupal 8 build. Each example file builds on the previous, with the most comprehensive being ```composer-custom.json```.
* ```composer-basic.json```: This file installs drupal core, and the required scaffold and installers packages. This is the bare minimum required for a drupal site on Acquia hosting.
* ```composer-contrib.json```: This file adds a few drupal contrib modules as well as two modules intended for develoment only.
* ```composer-libraries.json```:  This file builds on the previous two by illustrating how you can use Composer to add third-party dependencies, like libraries, and installs them is specific directories (the example is [drupal/file_browser](https://www.drupal.org/project/file_browser)).
* ```composer-custom.json```: This file adds in custom repos that are not on packagist.

Please see [Acquia Automation: Composer builds](https://docs.acquia.com/ra/automation/composer) for a detailed explanation of each section.

## Usage

1. Copy the ```composer.json``` file into the top level of your repository.
1. Add the specific drupal modules, themes and libraries that your site requires. You may do this by manually adding items to the ```require``` section of the ```composer.json``` or running the command ```composer require drupal/modulename```.
1. Ensure that ```drupal-composer/drupal-scaffold``` is required *before* ```drupal/core```.
1. Run ```composer update``` to install all code, vendor directories, etc.

You must commit all generated code to your Acquia repository!

## Resources

* [Composer](https://getcomposer.org/)
* [Acquia Remote Administration](https://docs.acquia.com/ra)
* [Acquia Automation](https://docs.acquia.com/ra/automation)
* [Acquia Automation: Composer builds](https://docs.acquia.com/ra/automation/composer)
