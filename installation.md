---
title: How to install package
description: How to install package
github: https://github.com/zaimea/metrics-docs/edit/main/
---

# Metrics

[[TOC]]

## Instalation

```json
"repositories": [
        {
            "type": "vcs",
            "url": "https://github.com/zaimealabs/metrics"
        }
    ]
```

```bash
composer require zaimealabs/metrics
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