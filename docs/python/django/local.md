# Locally
![](/opentelemetry-sqlcommenter/images/locally-logo.png)


- [Locally](#locally)
    - [Introduction](#introduction)
    - [Requirements](#requirements)
    - [Addition to your code](#addition-to-your-code)
    - [References](#references)


## Introduction

This guide will help you add [sqlcommenter](https://github.com/open-telemetry/opentelemetry-sqlcommenter) to your Django applications running locally.

Please see the reference for the fields added in the SQL comments [google-cloud-sqlcommenter.Fields](README.md/#fields)

## Requirements

| Steps                     | Resource                                             |
| ------------------------- | ---------------------------------------------------- |
| Django                    | <https://docs.djangoproject.com/en/stable/intro/>      |
| google-cloud-sqlcommenter | <https://pypi.org/project/google-cloud-sqlcommenter>   |
| Django 2.X                | <https://docs.djangoproject.com/en/stable/faq/install> |
| Python 3.X                | <https://www.python.org/downloads/>                    |

## Addition to your code

Firstly, please install [google-cloud-sqlcommenter](README.md#installation).

For any Django deployment, we can just edit our settings.py file and update the `MIDDLEWARE` section as per:

```python
# settings.py

MIDDLEWARE = [
  'google.cloud.sqlcommenter.django.middleware.SqlCommenter',
  ...
]
```

>If any middleware execute database queries (that you'd like commented by SqlCommenter), those middleware MUST appear after
'google.cloud.sqlcommenter.django.middleware.SqlCommenter'*


## References

| Resource                     | URL                                              |
| ---------------------------- | ------------------------------------------------ |
| Django quickstart            | <https://docs.djangoproject.com/en/stable/intro/>  |
| Installing Django middleware | [link](README.md/#installation) |