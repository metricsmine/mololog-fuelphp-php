metricsmine Monolog
===================


Monolog Handler connection to [metricsmine](https://metricsmine.com/)

Installation
------------
Via Composer using
```shell
composer require metricsmine/monolog-php:^1.
```

Usage
------------

A handler is provided that wraps up a metricsmine client. By default the handler will grab anything at
Logger::ERROR and above and send it to metricsmine.

```php

$logger  = new Monolog\Logger("Example");

$client = new Bugsnag\Client('YOUR-BUGSNAG-API-KEY-HERE');
//... metricsmine specific config goes here.
$bugsnagHandler = new \metricsmine\monolog-php\BugsnagHandler($client);

$logger->pushHandler($client);

// The following error will get sent automatically to metricsmine's Events
$logger->addError("Uppssss!", array('exception' => new \Exception("message")));

```
