# SwaggerClient-php
This API documentation describes all endpoints for orders

This PHP package is automatically generated by the [Swagger Codegen](https://github.com/swagger-api/swagger-codegen) project:

- API version: v2
- Package version: v1.0
- Build package: io.swagger.codegen.v3.generators.php.PhpClientCodegen

## Requirements

PHP 5.5 and later

## Installation & Usage
### Composer

To install the bindings via [Composer](http://getcomposer.org/), add the following to `composer.json`:

```
{
  "repositories": [
    {
      "type": "git",
      "url": "https://github.com/gisevevokoru/ezze-siftuz-orders-v2.git"
    }
  ],
  "require": {
    "gisevevokoru/ezze-siftuz-orders-v2": "*@dev"
  }
}
```

Then run `composer install`

### Manual Installation

Download the files and include `autoload.php`:

```php
    require_once('/path/to/SwaggerClient-php/vendor/autoload.php');
```

## Tests

To run the unit tests:

```
composer install
./vendor/bin/phpunit
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new EzzeSiftuz\OrdersV2\Api\ALLApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$sales_order_id = "sales_order_id_example"; // string | 
$position_item_id = array("position_item_id_example"); // string[] | 

try {
    $apiInstance->cancelPartnerOrderPositionItems($sales_order_id, $position_item_id);
} catch (Exception $e) {
    echo 'Exception when calling ALLApi->cancelPartnerOrderPositionItems: ', $e->getMessage(), PHP_EOL;
}

$apiInstance = new EzzeSiftuz\OrdersV2\Api\ALLApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$sales_order_id = array("sales_order_id_example"); // string[] | 

try {
    $apiInstance->cancelPartnerOrders($sales_order_id);
} catch (Exception $e) {
    echo 'Exception when calling ALLApi->cancelPartnerOrders: ', $e->getMessage(), PHP_EOL;
}

$apiInstance = new EzzeSiftuz\OrdersV2\Api\ALLApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$sales_order_id = "sales_order_id_example"; // string | 
$position_item_id = array("position_item_id_example"); // string[] | 

try {
    $apiInstance->confirmPartnerOrderPositionItems($sales_order_id, $position_item_id);
} catch (Exception $e) {
    echo 'Exception when calling ALLApi->confirmPartnerOrderPositionItems: ', $e->getMessage(), PHP_EOL;
}

$apiInstance = new EzzeSiftuz\OrdersV2\Api\ALLApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$sales_order_id = array("sales_order_id_example"); // string[] | 

try {
    $apiInstance->confirmPartnerOrders($sales_order_id);
} catch (Exception $e) {
    echo 'Exception when calling ALLApi->confirmPartnerOrders: ', $e->getMessage(), PHP_EOL;
}

$apiInstance = new EzzeSiftuz\OrdersV2\Api\ALLApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$from_date = new \DateTime("2013-10-20T19:20:30+01:00"); // \DateTime | Defines, which minimum lifecycle change date the returned order should have
$fulfillment_status = array("fulfillment_status_example"); // string[] | Defines, which minimum state the returned orders should have.<br>If ANNOUNCED is given, all orders, which have at least one position in ANNOUNCED state are returned.<br>If PROCESSABLE is given, all orders, which have at least one position in PROCESSABLE state and none in ANNOUNCED state are returned.<br>If CONFIRMED is given, all orders, which have at least one position in CONFIRMED state and none in either ANNOUNCED or PROCESSABLE state are returned.<br>If SENT is given, all orders, which have at least one position in SENT state and none in either ANNOUNCED or PROCESSABLE or CONFIRMED state are returned.<br>If RETURNED is given, all orders, which have at least one position in RETURNED state and none in either ANNOUNCED or PROCESSABLE or CONFIRMED or SENT state are returned.<br>If CANCELLED_BY_PARTNER is given, all orders, which have at least one position in CANCELLED_BY_PARTNER state are returned.<br>If CANCELLED_BY_MARKETPLACE is given, all orders, which have at least one position in CANCELLED_BY_MARKETPLACE state are returned.<br>If none is provided, all status will be returned.<br>Several values can be passed via request param array, when multiple values passed, search result will be combination of multiple fulfillmentStatuses - no duplicates will appear.<br>Example: ?fulfillmentStatus=PROCESSABLE,CONFIRMED&fulfillmentStatus=CANCELLED_BY_MARKETPLACE - will return orders in these 3 fulfillmentStatuses.<br>Alternatively, mode can be passed for a different search type. BUCKET/AT_LEAST_ONE, where BUCKET is default behaviour explained above and AT_LEAST_ONE checks if there is at least 1 position item with passed fulfillmentStatus/fulfillmentStatuses.
$limit = 56; // int | limit
$order_direction = "order_direction_example"; // string | Ordering direction ASC/DESC
$order_column_type = "order_column_type_example"; // string | Column by which to order partnerOrders
$mode = "mode_example"; // string | Mode for type of search, default mode is bucket
$nextcursor = "nextcursor_example"; // string | For paging request this cursor is required. If a next cursor is provided, the only other request parameter being considered is 'limit'.
$search_term = "search_term_example"; // string | Partial Text Search

try {
    $result = $apiInstance->findPartnerOrders($from_date, $fulfillment_status, $limit, $order_direction, $order_column_type, $mode, $nextcursor, $search_term);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ALLApi->findPartnerOrders: ', $e->getMessage(), PHP_EOL;
}

$apiInstance = new EzzeSiftuz\OrdersV2\Api\ALLApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$sales_order_id = "sales_order_id_example"; // string | 

try {
    $result = $apiInstance->getPartnerOrderBySalesOrderId($sales_order_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ALLApi->getPartnerOrderBySalesOrderId: ', $e->getMessage(), PHP_EOL;
}
?>
```

## Documentation for API Endpoints

All URIs are relative to *https://live.api.otto.market/v2*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*ALLApi* | [**cancelPartnerOrderPositionItems**](docs/Api/ALLApi.md#cancelpartnerorderpositionitems) | **POST** /orders/{salesOrderId}/items/{positionItemId}/cancellation | Cancel a single position item
*ALLApi* | [**cancelPartnerOrders**](docs/Api/ALLApi.md#cancelpartnerorders) | **POST** /orders/{salesOrderId}/cancellation | Cancel all position items on a order. Note, only position items in the state PROCESSABLE or CONFIRMED get changed. All other position items get not changed
*ALLApi* | [**confirmPartnerOrderPositionItems**](docs/Api/ALLApi.md#confirmpartnerorderpositionitems) | **POST** /orders/{salesOrderId}/items/{positionItemId}/confirmation | Confirm a single position item
*ALLApi* | [**confirmPartnerOrders**](docs/Api/ALLApi.md#confirmpartnerorders) | **POST** /orders/{salesOrderId}/confirmation | Confirm all position items on an order. Note, only position items in the state PROCESSABLE get changed. All other position items get not changed
*ALLApi* | [**findPartnerOrders**](docs/Api/ALLApi.md#findpartnerorders) | **GET** /orders | Get a list of orders which can be filtered on fulfillmentStatus.
*ALLApi* | [**getPartnerOrderBySalesOrderId**](docs/Api/ALLApi.md#getpartnerorderbysalesorderid) | **GET** /orders/{salesOrderId} | Get a single order via Sales Order Id
*ItemsApi* | [**cancelPartnerOrderPositionItems**](docs/Api/ItemsApi.md#cancelpartnerorderpositionitems) | **POST** /orders/{salesOrderId}/items/{positionItemId}/cancellation | Cancel a single position item
*ItemsApi* | [**confirmPartnerOrderPositionItems**](docs/Api/ItemsApi.md#confirmpartnerorderpositionitems) | **POST** /orders/{salesOrderId}/items/{positionItemId}/confirmation | Confirm a single position item
*OrdersApi* | [**cancelPartnerOrders**](docs/Api/OrdersApi.md#cancelpartnerorders) | **POST** /orders/{salesOrderId}/cancellation | Cancel all position items on a order. Note, only position items in the state PROCESSABLE or CONFIRMED get changed. All other position items get not changed
*OrdersApi* | [**confirmPartnerOrders**](docs/Api/OrdersApi.md#confirmpartnerorders) | **POST** /orders/{salesOrderId}/confirmation | Confirm all position items on an order. Note, only position items in the state PROCESSABLE get changed. All other position items get not changed
*OrdersApi* | [**findPartnerOrders**](docs/Api/OrdersApi.md#findpartnerorders) | **GET** /orders | Get a list of orders which can be filtered on fulfillmentStatus.
*OrdersApi* | [**getPartnerOrderBySalesOrderId**](docs/Api/OrdersApi.md#getpartnerorderbysalesorderid) | **GET** /orders/{salesOrderId} | Get a single order via Sales Order Id

## Documentation For Models

 - [Address](docs/Model/Address.md)
 - [Amount](docs/Model/Amount.md)
 - [InitialServiceFee](docs/Model/InitialServiceFee.md)
 - [Link](docs/Model/Link.md)
 - [OrderLifecycleInformation](docs/Model/OrderLifecycleInformation.md)
 - [PartnerOrder](docs/Model/PartnerOrder.md)
 - [PartnerOrderList](docs/Model/PartnerOrderList.md)
 - [PositionItem](docs/Model/PositionItem.md)
 - [Product](docs/Model/Product.md)

## Documentation For Authorization

 All endpoints do not require authorization.


## Author



