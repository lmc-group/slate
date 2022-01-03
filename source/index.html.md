---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true

code_clipboard: true
---

# Introduction

Welcome to the LMC Auto API. You can use our API to access insider data, ...

# Authentication

Please contact our sales to create you an account. You will get a username and password.
They are always required to authen to our API.

`Authorization: awesomelmc`

<aside class="notice">
Assume that <code>awesomelmc</code> is your API key, it is base 64 encoded of your username and password.
</aside>

# Data Endpoint

## Retrieve table data

```shell
curl "http://api.lmc-auto.com/v1/data?table_name=country&result_format=json" \
  -H "Authorization: awesomelmc"
```

> The above command returns JSON structured like this:

```json
[    
    {
        "country_id": "152",
        "country": "Algeria",
        "region_id": "10",
        "last_sales_actual": "Dec-2021"
    },
   {
        "country_id": "258",
        "country": "Botswana",
        "region_id": "10",
        "last_sales_actual": "Dec-2021"
    },
]
```

This endpoint retrieves a specific table.

### HTTP Request

`GET http://example.com/api/data`

### URL Parameters

Parameter | Description
--------- | -----------
table_name | Table name
result_format | json or csv
region | This is needed for some tables
filter | (optional) refered to https://github.com/TRUEPIC/queryql/blob/development/DOCS.md#filtering
sort | (optional) refered to https://github.com/TRUEPIC/queryql/blob/development/DOCS.md#sorting

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

# Download Endpoint

## List downloadable contents

## Retrieve downloadable content