---
title: How to install package
description: How to install package
github: https://github.com/zaimea/metrics-docs/edit/main/
---

# Metrics

[[TOC]]

## Introduction

This package will help you create ``metrics`` for your models to generate, for example: invoice numbers in your ``Laravel`` application.

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