# Acquia Remote Administration Composer Build Example
[Composer](https://getcomposer.org/) builds allow [Acquia Remote Administration (RA)](https://docs.acquia.com/ra) clients to efficiently include various scripts and patches, including post-update builds.

[Acquia Automation](https://docs.acquia.com/ra/automation) will update Composer built websites whose repositories conform to the proper architecture and include a fully-functioning ```composer.json``` file that builds a Drupal website.

This repository contains a sample ```composer.json``` file which can be used to start a working Drupal 8 build. The file contains a few basic drupal modules as well as an example of adding third-party dependencies (for [drupl/file_browser](https://www.drupal.org/project/file_browser)). Please see [Acquia Automation: Composer builds](https://docs.acquia.com/ra/automation/composer) for a detailed explanation of each section.

## Usage

1. Copy the composer.json file of your choice into the top level of your repository.
1. Add the specific drupal modules, themes and libraries that your site requires. You may do this by manually adding items to the ```require``` section of the ```compser.json``` or running the command ```composer require drupal/modulename```.
1. Run ```composer update``` to install all code, vendor directories, etc.

You must commit all generated code to your Acquia repository!

## Resources

* [Composer](https://getcomposer.org/)
* [Acquia Remote Administration](https://docs.acquia.com/ra)
* [Acquia Automation](https://docs.acquia.com/ra/automation)
* [Acquia Automation: Composer builds](https://docs.acquia.com/ra/automation/composer)
