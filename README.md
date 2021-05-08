# Skysail

## Introduction

A quick and easy php framework, for easy low-friction creation of APIs

## Prerequisites

This API makes use of composer, as such, you will need that installed.
To run the application, you will need to run `composer install --no-dev` to generate the Autoloader bindings for `index.php` the API.

## Testing

To run tests you must first run `composer install` to allow composer to get PHPUnit.

Then Run `./vendor/bin/phpunit` this will pick up the `phpunit.xml` settings file from the project root and run the test suite.

## Routing

This library supports routing, however, to do so requires some server configuration to rewrite requests to index.php (or whichever file you are running Skysail from)

### Example .htaccess

```
RewriteEngine on

RewriteCond %{REQUEST_FILENAME} !-d
RewriteCond %{REQUEST_FILENAME} !-f
RewriteRule ^(.+)$ index.php?url=$1 [QSA,L]
```
