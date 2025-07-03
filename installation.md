---
title: How to install Metrics package
description: How to install Metrics package
github: https://github.com/zaimea/metrics-docs/edit/main/
---

# Metrics

[[TOC]]

## Instalation

You can install the package via composer:

```bash
composer require zaimealabs/metrics
```

or via composer.json

```json
"repositories": [
        {
            "type": "vcs",
            "url": "https://github.com/zaimealabs/metrics"
        }
    ]
```


## Publish

```bash
    php artisan vendor:publish --tag=metric
```

## Migrations

Run migrations to create matrics table in your database
```bash
    php artisan migrate
```
