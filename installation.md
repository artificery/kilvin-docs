
# Install Kilvin CMS

### Server Requirements
 - PHP 7.0 or later with safe mode disabled
 - MySQL 5.5.0 or later, with the InnoDB storage engine installed. MariaDB works too.
 - A web server (Apache, Nginx)
 - OpenSSL PHP Extension
 - PDO PHP Extension
 - Mbstring PHP Extension
 - Tokenizer PHP Extension

### Installation

 - Insure you have a server meeting the above requirements. [Laravel Homestead](https://laravel.com/docs/5.4/homestead) is a superb development environment for Kilvin CMS.
 - Clone this GitHub repo onto your server.
 - In your terminal, run the following [Composer](https://getcomposer.org) command in your cloned directory to install Kilvin's dependencies: `composer create-project --prefer-dist`.
 - Permissions. Insure that the following files and directories are writeable on your server. Homestead is set up to allow this automatically:
   - .env
   - cms/storage
   - cms/templates
   - public/images
 - Create a database for your new site in MySQL/MariaDB.
 - Configure your webserver to make the `./public` directory your web root.
 - Direct your browser to the install.php file on your new site and run the installer. Example: http://mysite.com/install.php