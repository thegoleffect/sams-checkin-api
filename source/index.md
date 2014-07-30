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


# Store Orders

## Get All Orders By Store

```shell
# ohai
curl https://api.samsclub.com/cnp/
```

```javascript
var Request = require('request');

// TODO
```



> The above command returns JSON structured like this:

```json
{
  "key": "value"
}
```

This endpoint retrieves all the orders for a given store.

### HTTP Request

`GET https://internal-api.samsclub.com/cnp/stores/{id}/orders`

### URL Parameters

Parameter | Description
--------- | -----------
id | Store ID


## Get a Specific Order

```javascript
#!/usr/bin/env node
var Request = require('request');

var req = {
  
};
Request(req, function(err, res, body){
  
});
```

```shell
curl https://api.samsclub.com/cnp/stores/{id}/orders`
```


> The above command returns JSON structured like this:

```json
{
  "status": 1
}
```

This endpoint retrieves a specific order.

### HTTP Request

`GET https://internal-api.samsclub.com/cnp/stores/{id}/orders/{oid}`

### URL Parameters

Parameter | Description
--------- | -----------
id | Store ID
oid | Order ID


# Order Status

## Update Order Status

```shell
# todo
```

```javascript
//todo
```

TODO

## Listen for Status Updates

This is a long-poll capable endpoint.

```shell
# todo
```

```javascript

```

TODO


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

`POST https://api.samsclub.com/cnp/customer/status`


### Header Parameters

Parameter | Default | Description
--------- | ------- | -----------
wm.? | null | Authentication cookie


## Location Update

This endpoint reports GPS or geofence location data from clients.

## 