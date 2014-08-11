Parcelforce expressTransfer API for Laravel 4
======================
This package generates pre-advice electronic file that required by [**Parcelforce**]
(http://www.parcelforce.com/) exrpessTransfer solution in order to arrange collection or dispatches.

[![Build Status](https://travis-ci.org/alexpechkarev/parcelforce.svg?branch=master)](https://travis-ci.org/alexpechkarev/parcelforce)



Features
------------

 - Generating electronic file on the server
 - Submitting electronic file to [**Parcelforce**](http://www.parcelforce.com/)
 - Single or multiply consignment's per file
 - UK Domestic collection request (Label and receipt provided by PFW driver) 
 - UK Domestic services dispatches only (Label printed by customer)


        
Requirements
------------

Must be [**Parcelforce**](http://www.parcelforce.com/) customer        
PHP >= 5.3        
MySQL
        
Using as [**Laravel 4**](http://laravel.com/) package version 4.1 or above required



Installation
------------


To install edit `composer.json` and add following line:

```php
"parcelforce/exrpesstransfer": "dev-master"
```

Run `composer update`



Configuration
-------------

Once installed, register Laravel service provider, in your `app/config/app.php`:

```php
'providers' => array(
	...
    'Parcelforce\ExpressTransfer\ParcelforceServiceProvider',
)
```


Publish configuration file:

```php

php artisan config:publish parcelforce/expresstransfer --path vendor/parcelforce/expresstransfer/src/config/

```

Folder `files` must be writable by web server

```php

chmod o+w app/config/packages/parcelforce/expresstransfer/files

```


Laravel PHPUnit Testing
-------------

Install Mockery 
```
composer require mockery/mockery:dev-master@dev
```

Copy test and dataset file to app/tests
```
cp vendor/parcelforce/expresstransfer/tests/ParcelforceTest.txt app/tests/ParcelforceTest.php


phpunit app/tests/ParcelforceTest.php
```