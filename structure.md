

# Directory Structure

- [Introduction](#introduction)
- [The Root Directory](#root-directory)
    - [The `app` Directory](#app-directory)
    - [The `config` Directory](#config-directory)
    - [The `templates` Directory](#templates-directory)
    - [The `tests` Directory](#tests-directory)
    - [The `vendor` Directory](#vendor-directory)

<a name="introduction"></a>
## Introduction

If you have never used the [Laravel PHP Framework](https://laravel.com) or [Composer](https://getcomposer.org/) before, then it is important for you to understand that a significant portion of the code used to run Kilvin CMS is contained within "packages" from multiple developers that are located in the `./vendor` directory of your site. These packages are found and downloaded by the Composer command line tool and installed based off specific requirements set by Kilvin CMS and any libraries it depends on. You should NEVER modify the code within the `./vendor` directory as your changes will be overwritten on the next update.

For example, all of the core Kilvin CMS code—including CSS, JS, and images—for rendering the Kilvin CMS control panel and outputting your weblog data in templates is located in `./vendor/artificery/kilvin-cms`  directory of your site.

Since the Kilvin CMS is built on top of the Laravel PHP Framework, its structure is very similar to [the one that Laravel starts with](https://github.com/laravel/laravel). This is completely intentional and means that you can expand your site to use Laravel features completely outside of Kilvin CMS. The news and blog portion of your site could be managed by Kilvin CMS, and then a completely separate API-based application could be built within Laravel. Separate data sources, caching, and even social integrations are possible.


<a name="root-directory"></a>
## Root Directory

We suggest you take a gander at the [Root Directory](https://laravel.com/docs/structure#the-root-directory) section of the Laravel documentation to get a better understanding of what the default folders do. Below we explain any changes and additions the Kilvin CMS has made.

<a name="app-directory"></a>
#### The App Directory

The `app` directory contains the core code of your Laravel application. Kilvin CMS uses a [Service Provider](https://laravel.com/docs/providers) to expand Laravel and add its own application code that is located in the `./vendor` directory

The only file that has been modified from the standard Laravel version is `Handler/Exceptions.php`, which is not a child of the Kilvin CMS Exception Handler.

<a name="config-directory"></a>
#### The Config Directory

The `config` directory contains all of your application's configuration files.

- **filesystems.php** - Kilvin CMS has its own filesystem configuration options called Asset Containers. Any filesystems set up in this config file will not be accesible to it, for security reasons. 

- **kilvin.php** - A few Kilvin CMS configuration options, which are settable via your [environment file](https://laravel.com/docs/5.7/configuration#environment-configuration). 

- **twig.php** - Kilvin CMS uses the [Twig templating engine](https://twig.symfony.com/) for its site templates. This file contains the configuration options for this templating engine, including what functions to use within the templates for outputting Kilvin CMS and Laravel information.

<a name="templates-directory"></a>
#### The Templates Directory

The `templates` directory contains all of the templates for your sites, which allows them to be stored in version control. Each site has its own directory and there is also a `_global` directory that contains Twig templates that can be used by any site.

Each site can have its own `_errors` folder for things like a 404 error, when a request is made for a page that does not exist. If a site does not have an `_errors` folder, the global `_errors` templates are used instead.

<a name="tests-directory"></a>
#### The Tests Directory

The `tests` directory contains your automated tests. A number of basic tests are provided, which can be used to test whether the Kilvin CMS is running correctly. Each test class should be suffixed with the word `Test`. You may run your tests using the `phpunit` or `php vendor/bin/phpunit` commands.

<a name="vendor-directory"></a>
#### The Vendor Directory

The `vendor` directory contains your [Composer](https://getcomposer.org) dependencies.