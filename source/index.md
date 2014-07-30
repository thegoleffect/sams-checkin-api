---
title: API Reference

language_tabs:
  - shell
  - javascript

toc_footers:
  - <a href='http://github.com/tripit/slate'>Documentation Powered by Slate</a>

search: true
---

# Introduction

Welcome to the Sam's Club Checkin API documentation. This is a **draft**.

This API will be accessed by in-store Kiosks.

# Authentication

> To authorize, use this code:

```shell
# TODO
```

```javascript
// TODO
```

TODO


# Orders

## List Customer IDs with Open Orders

```javascript
#!/usr/bin/env node
var Request = require('request');

var req = {
  
};
Request(req, function(err, res, body){
  
});
```

```shell
curl $HOST/cnp/stores/{id}/customers`
```


> The above command returns JSON structured like this:

```json
{
    "data": {
        "0001": 1406738014324,
        "0002": 1406738014324
    }
}
```

This endpoint retrieves a list of customers with open orders at a given store. The response will include a JSON object with customer ID as keys and timestamps as values. The timestamps represent when the order was uploaded to our system.

### HTTP Request

`GET $HOST/cnp/stores/{id}/customers`

### URL Parameters

Parameter | Description
--------- | -----------
id | Store ID


### Response Parameters

Parameter | Description
--------- | -----------
data | JSON hash customer-ids to created timestamps (or error message if statusCode is not 200)


## Upload Customer IDs by Store

```shell
curl -X POST $HOST/cnp/stores/{id}/orders \
    -d "cids[]=001&cids[]=002"
```

```javascript
var Request = require('request');

// TODO
```



> The above command returns JSON structured like this:

```json
{
  "data": "OK"
}
```

This endpoint is used by Stores to upload their list of customer IDs with open orders.

### HTTP Request

`POST $HOST/cnp/stores/{id}/customers`

### URL Parameters

Parameter | Description
--------- | -----------
id | Store ID

### POST Parameters

Parameter | Description
--------- | -----------
cids | Array of customer ids




# Status Change

## Update Order Status

```shell
curl -X POST $HOST/cnp/stores/{id}/customers/{cid} \
    -d "status=picked"
```

```javascript
//todo
```

This endpoint is used by Stores to update the order status of a single customer (picked up). 

### HTTP Request

`POST $HOST/cnp/stores/{id}/customers/{cid}`

### URL Parameters

Parameter | Description
--------- | -----------
id | Store ID
cid | Customer ID

### POST Parameters

Parameter | Values | Description
--------- | ----------- | -----------
status | 'picked','noshow' | String to indicate order status.


## Listen for Status Changes

This is a long-poll capable endpoint.

```shell
# todo
```

```javascript

```

This endpoint is used by Stores to listen for customer ETA updates. 

### HTTP Request

`GET $HOST/cnp/stores/{id}`

### URL Parameters

Parameter | Description
--------- | -----------
id | Store ID


# Notifications

## Send Order Ready

```shell
# todo
```

```javascript
//todo
```
TODO

# Customers

## Pre-checkin

This endpoint announces the customer's intent to visit the store.

### HTTP Request

`POST $HOST/cnp/customer/status`

### Post Parameters

Parameter | Description
--------- | -----------
precheckin | 

### Header Parameters

Parameter | Default | Description
--------- | ------- | -----------
wm.? | null | Authentication cookie


## Location Update

This endpoint reports GPS or geofence location data from clients.

### HTTP Request

`POST $HOST/cnp/customer/status`