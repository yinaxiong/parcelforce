Parcelforce API for Lavarel 4
======================

[![Build Status](https://travis-ci.org/alexpechkarev/parcelforce.svg?branch=master)](https://travis-ci.org/alexpechkarev/parcelforce)

Installation
------------


To install edit `composer.json` and add following line:

```javascript
"alexpechkarev/parcelforce": "dev-master"
```

Run `composer update`



Configuration
-------------

Once installed, register Laravel service provider, in your `app/config/app.php`:

```php
'providers' => array(
	...
    'Alexpechkarev\Parcelforce\ParcelforceServiceProvider',
)
```


Publish configuration file:

```php

php artisan config:publish alexpechkarev/parcelforce --path vendor/alexpechkarev/parcelforce/src/config/

```

Make files folder writable by web server

```php

chmod o+w app/config/packages/alexpechkarev/parcelforce/files

```


Testing
-------------

Install Mockery 
```
composer require mockery/mockery:dev-master@dev
```

Copy test and dataset file to app/tests
```
cp vendor/alexpechkarev/parcelforce/tests/ParcelforceTest.txt app/tests/ParcelforceTest.php

cp vendor/alexpechkarev/parcelforce/tests/setRecordResponse app/tests/

phpunit app/tests/ParcelforceTest.php
```