---
title: How to use package
description: How to use package
github: https://github.com/zaimea/metrics-docs/edit/main/
---

# Metrics Usage

[[TOC]]

## Introduction

Using this package you will be able to have a record of the numbers, for example: invoices are issued and a numbered record is needed for each invoice, this package fulfills exactly what you are looking for.

## Usage

Set your enums in our config (config/metric.php)

Add HasMetrics trait to your model
```php
    use ZaimeaLabs\Metrics\HasMetrics;

    class User extends Authenticable
    {
        use HasMetrics;
    }
```

## With config enums

Increment
```php
    $user->incrementMetric(config('metric.enums.Logins'), 1);
```
Decrement
```php
    $user->decrementMetric(config('metric.enums.Logins'), 1);
```
Get value
```php
    $user->metrics()->where('name', 'logins')->value('value');
```

## Or use with Enums

Create your enum
```php
    enum UserMetric: string
    {
        case Logins = 'logins';
    }
```

Increment
```php
    $user->incrementMetric(UserMetric::Logins->value, 1);
```
Decrement
```php
    $user->decrementMetric(UserMetric::Logins->value, 1);
```
Get value
```php
    $user->metrics()->where('name', 'logins')->value('value');
```

Don't increment/decrement with month,year
```php
    $user->incrementMetric(UserMetric::Logins->value, 1, /*withDate*/ false);

    $user->decrementMetric(UserMetric::Logins->value, 1, /*withDate*/ false);
```

Increment/decrement with specific month,year
```php
    $user->incrementMetric(UserMetric::Logins->value, /*withDate*/ 1, true, /*month*/ 04, /*year*/ 2023, /*day*/ 01);

    $user->decrementMetric(UserMetric::Logins->value, /*withDate*/ 1, true, /*month*/ 04, /*year*/ 2023, /*day*/ 01);
```
