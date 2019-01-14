
# Install Kilvin CMS

### Server Requirements
 - PHP 7.1.3 or later with safe mode disabled
 - MySQL 5.5.0 or later, with the InnoDB storage engine installed. MariaDB works too.
 - A web server (Apache, Nginx)
 - OpenSSL PHP Extension
 - PDO PHP Extension
 - Mbstring PHP Extension
 - Tokenizer PHP Extension

### Installation

 - Insure you have a server meeting the above requirements. [Laravel Homestead](https://laravel.com/docs/5.4/homestead) is a superb development environment for Kilvin CMS.
 - Clone the [Kilvin CMS starter repo](https://github.com/artificery/kilvin) onto your server.
 - In your terminal, run the following [Composer](https://getcomposer.org) command in your cloned directory to install Kilvin's dependencies: `composer create-project --prefer-dist`.
 - Permissions. Insure that the following files and directories are writeable on your server. Homestead is set up to allow this automatically:
   - .env
   - cms/storage
   - cms/templates
   - public/images
 - Configure your webserver to make the `./public` directory your web root.
 - Create a database for your new site in MySQL/MariaDB.
 - Direct your browser to the `/installer` URL on your new site and run the installer. Example: https://mysite.com/installer
 - Go through the installer steps to install the CMS.
 - That's it! After completion, the installer will direct you to your Kilvin CMS control panel for the site.