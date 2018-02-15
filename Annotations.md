# Acquia RA composer.json Template w/Annotations
[Name and Description](#name-and-description)
[Type](#type)  
[License](#license)  
[Repositories](#repositories)  
[Require](#require)  
[Require-Dev](#require-dev)  
[Conflict](#conflict)  
[Minimum-Stability](#minimum-stability)  
[Prefer-Stable](#prefer-stable)  
[Extra](#extra)  
[Installer-Paths](#installer-paths)  
[Scripts](#scripts)  
[Patches](#patches)  
#### Name and Description
```
{
    "name": "acquia/acquia-ra-composer",
    "description": "Project json for Acquia Remote Administration Composer builds",
```
This is the name of your project and a brief description of what your project consists of.
#### Type
```
    "type": "project",
```
Types are used througout your composer.json. You can find more information here:
[composer.org: Schema](https://getcomposer.org/doc/04-schema.md#type)
#### License
```
    "license": "proprietary",
```
You can specify the type of license that is most appropriate to for your project. You can review additional license types at  getcomposer.org:
[composer.org: License](https://getcomposer.org/doc/04-schema.md#license)
#### Repositories
```
    "repositories": {
        "drupal": {
            "type": "composer",
            "url": "https://packages.drupal.org/8"
        }
    },
```
By default, Composer will look for packages on packagist.org. You can add additional repositories to check against in this section:
[composer.org: Repositories](https://getcomposer.org/doc/04-schema.md#repositories)
#### Require
```
    "require": {
        "composer/installers": "^1.0",
        "cweagans/composer-patches": "^1.6.0",
        "drupal-composer/drupal-scaffold": "^2.0.0",
        "drupal/admin_toolbar": "^1.0",
        "drupal/core": "^8.4",
        "drush/drush": "^9.0"
    },
```
This section is a list of the dependencies that are installed in your project:
[composer.org: Require](https://getcomposer.org/doc/04-schema.md#require)
#### Require-Dev
```
    "require-dev": {
        "drupal/devel": "^1.0",
        "drupal/stage_file_proxy": "^1.0"
    },
```
This is a list of dependencies that are only required by your development team while working on the site itself:
[composer.org: Require-Dev](https://getcomposer.org/doc/04-schema.md#require-dev)
#### Conflict
```
    "conflict": {
        "drupal/core": "7.*"
    },
```
You can specify dependencies that would conflict with other dependencies in your project here:
[composer.org: Conflict](https://getcomposer.org/doc/04-schema.md#conflict)
#### Minimum-Stability
```
    "minimum-stability": "dev",
```
All dependencies added to your project must be at a version that at least matches or exceeds what is specified in your minimum-stability requirements. If one or more of your dependencies must be installed at a version that does not meet this requirement, you can do so by including the stability in the version. For example, to install version 1.0-rc1 of a project, you would add it using composer:
“composer require drupal/<project_name>:1.0-rc1@rc”
[composer.org: Minimum Stability](https://getcomposer.org/doc/04-schema.md#minimum-stability)
#### Prefer-Stable
```
    "prefer-stable": true,
```
When composer is adding or updating a dependency, it can choose a stable release or non-stable release as long as it conforms to your minimum-stability requirements:
[composer.org: Prefer-Stable](https://getcomposer.org/doc/04-schema.md#prefer-stable)
#### Extra
```
    "extra": {
```
The extra section is where dependency or project specific statements are added. Composer doesn't require these, but some of the dependencies that you add via composer can place additional settings, scripts or instructions here:
[composer.org: Extra](https://getcomposer.org/doc/04-schema.md#extra)
#### Installer-Paths
```
        "installer-paths": {
            "docroot/core": ["type:drupal-core"],
            "docroot/modules/contrib/{$name}": ["type:drupal-module"],
            "docroot/profiles/contrib/{$name}": ["type:drupal-profile"],
            "docroot/themes/contrib/{$name}": ["type:drupal-theme"],
            "docroot/libraries/{$name}": ["type:drupal-library"]
        }
    },
```
The composer/installers dependency that was included in the require section can be used to specify where other projects are installed:
[Project: composer/installers](https://github.com/composer/installers)
#### Scripts
```
    "scripts": {
        "post-install-cmd": [
            "@composer drupal-scaffold"
        ],
        "post-update-cmd": [
            "@composer drupal-scaffold"
        ],
        "drupal-scaffold": [
            "DrupalComposer\\DrupalScaffold\\Plugin::scaffold"
        ]
    },
    "enable-patching": true,
```
Paths to script files or specific commands can be included here and would be run a specific times during the install or update process:
[composer.org: Sripts](https://getcomposer.org/doc/04-schema.md#scripts)
#### Patches
```
    "patches": {
		"drupal/[module_name]": {
			"Note regarding the nature of the patch being applied": "https://www.drupal.org/files/issues/[patch_name].patch"     
		}
	}
}
```
If your project requires that patches be applied to some of your dependencies, you can include the name of the dependency to be patched as well as a path or url to a patch file. If no patches are required, you can remove this section as well as the cweagans/composer-patches dependency in the require section:
[Project: cweagans/composer-patches](https://github.com/cweagans/composer-patches)
