# Laravel 5 Workbench

### Installation

You can install the package via composer command line by runnign this following command.

```
composer require pingpong/workbench
```

After the package installed, add `Pingpong\Workbench\WorkbenchServiceProvider` to your `providers` array in `config/app.php` file.

And the last, publish the package's configuration by running:

```
php artisan vendor:publish
```

## Autoloading Workbench

You can autoload the workbench by adding this following command to your `bootstrap/autoload.php` file. Put this following command at the very bottom of script.

```php
/*
|--------------------------------------------------------------------------
| Register The Workbench Loaders
|--------------------------------------------------------------------------
|
| The Laravel workbench provides a convenient place to develop packages
| when working locally. However we will need to load in the Composer
| auto-load files for the packages so that these can be used here.
|
*/
if (is_dir($workbench = __DIR__.'/../workbench'))
{
	Pingpong\Workbench\Starter::start($workbench);
}
```

### Creating A Package

> Before you create a package, you need to update `name` and `email` config value in your `config/workbench.php` file. 

Creating a basic package.

```
php artisan workbench vendor/package
```

Creating a package with generating some scaffold resources.

```
php artisan workbench vendor/package --resources
```

### Other Documentation

> For more documentation you can visit [the official laravel documentation](http://laravel.com/docs/5.1/packages)
