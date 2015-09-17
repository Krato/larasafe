## Larasafe
An easy way to make backups of you laravel app.

[![Latest Stable Version](https://poser.pugx.org/krato/larasafe/v/stable.png)](https://packagist.org/packages/krato/larasafe) [![Total Downloads](https://poser.pugx.org/krato/larasafe/downloads.png)](https://packagist.org/packages/krato/larasafe) [![Latest Unstable Version](https://poser.pugx.org/krato/larasafe/v/unstable.png)](https://packagist.org/packages/krato/larasafe) [![License](https://poser.pugx.org/krato/larasafe/license.png)](https://packagist.org/packages/krato/larasafe)


![php artisan backup](http://goh.com.br/larasafe.png)

###Install
 - You need to require this package as a composer dependency, so, run:

    `composer require hernandes/larasafe:dev-master`

 - After it, register the package on the `$providers` array on `app/config/app.php`

 ~~~
 'providers' => array(

    'Illuminate\Foundation\Providers\ArtisanServiceProvider',
    'Illuminate\Auth\AuthServiceProvider',
    ...
    'Hernandes\Larasafe\LarasafeServiceProvider',
),
 ~~~

### Configuration
 - First thing we need to use it, is publish the package config files, do it running:

 `php artisan config:publish hernandes/larasafe`

 - Now we have 3 files inside `app/config/packages/hernandes/larasafe`

   - `database.php`

   		Where you need to setup your database connection to be used when backuping, you can also specify tables to ignore and aditional options to `mysqldump` command.
   - `files.php`

   		On files.php, you can choose what folders and files of your project need to be backed up, and some fine tune options, like what compression use.
   - `targets.php`

   		On targets.php, you will need to inform where you backups should be stored, supports local folders and remote servers, also, you can specify how much time backups should be preserved (rotation).


### Usage
After all this work, just run

`php artisan backup`

and be happy!

