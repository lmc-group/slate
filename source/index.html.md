---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - python

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

`Authorization: lmcawesome`

<aside class="notice">
Assume that <code>lmcawesome</code> is your API key, it is base 64 encoded of your username and password.
</aside>

# Data Endpoint

## Retrieve table data

```shell
curl "http://api.lmc-auto.com/v1/data?table_name=country&result_format=json" \
  -H "Authorization: lmcawesome"
```

```python
import requests

url = "https://api.lmc-auto.com/v1/data?table_name=country&result_format=json"

payload={}
headers = {
  'Authorization': 'Basic lmcawesome'
}

response = requests.request("GET", url, headers=headers, data=payload)

print(response.text)
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

`GET http://api.lmc-auto.com/v1/data`

### URL Parameters

Parameter | Description
--------- | -----------
table_name | Table name
result_format | json or csv
region | This is needed for some tables
filter | (optional) please refer to [QueryQL](https://github.com/TRUEPIC/queryql/blob/development/DOCS.md#filtering)
sort | (optional) please refer to [QueryQL](https://github.com/TRUEPIC/queryql/blob/development/DOCS.md#sorting)

# Download Endpoint

## List downloadable contents

```shell
curl "http://api.lmc-auto.com/v1/downloads" \
  -H "Authorization: lmcawesome"
```

```python
import requests

url = "https://api.lmc-auto.com/v1/downloads"

payload={}
headers = {
  'Authorization': 'Basic lmcawesome'
}

response = requests.request("GET", url, headers=headers, data=payload)

print(response.text)

```

> The above command returns JSON structured like this:

```json
[
    "LMCA_[SA_LVPF(BS)]_Capa_Data.csv",
    "LMCA_[SA_LVPF(BS)]_Data.csv"
]
```

This endpoint lists the downloadable contents.

### HTTP Request

`GET http://api.lmc-auto.com/v1/downloads`

### URL Parameters

Parameter | Description
--------- | -----------
None | None

## Retrieve downloadable content

```shell
curl "http://api.lmc-auto.com/v1/download?file_name=example.csv" \
  -H "Authorization: lmcawesome"
```

```python
import requests

url = "https://api.lmc-auto.com/v1/download?file_name=example.csv"

payload={}
headers = {
  'Authorization': 'Basic lmcawesome'
}

response = requests.request("GET", url, headers=headers, data=payload)

print(response.text)

```

> The above command returns CSV comma separated like this:

```csv
PublishVersion,Country,Manufacturer,Year,Plant_Code,Plant_Name,Local_Manufacturing_Partner,Location,Publish_Region,Market,Last_Production_Actual,City,Latitude,Longitude,Capacity,Utilization
20210301,Brazil,Grupo CAOA,2016,ACA,Anapolis,,Goias,South America,Splits Mercosur,2020-12-01 00:00:00,Anapolis,-16.3996088,-48.906932,86400,0.26265116275
20210301,Brazil,Grupo CAOA,2017,ACA,Anapolis,,Goias,South America,Splits Mercosur,2020-12-01 00:00:00,Anapolis,-16.3996088,-48.906932,86400,0.22533720933333337
20210301,Brazil,Grupo CAOA,2018,ACA,Anapolis,,Goias,South America,Splits Mercosur,2020-12-01 00:00:00,Anapolis,-16.3996088,-48.906932,86400,0.24545348833333336
20210301,Brazil,Grupo CAOA,2019,ACA,Anapolis,,Goias,South America,Splits Mercosur,2020-12-01 00:00:00,Anapolis,-16.3996088,-48.906932,86400,0.27709302316666667
```

This endpoint retrieves a specific downloadable content.

### HTTP Request

`GET http://api.lmc-auto.com/v1/download`

### URL Parameters

Parameter | Description
--------- | -----------
file_name | The file name that you retrieve from List downloadable contents API