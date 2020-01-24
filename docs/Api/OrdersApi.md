# EzzeSiftuz\OrdersV2\OrdersApi

All URIs are relative to *https://live.api.otto.market/v2*

Method | HTTP request | Description
------------- | ------------- | -------------
[**cancelPartnerOrders**](OrdersApi.md#cancelpartnerorders) | **POST** /orders/{salesOrderId}/cancellation | Cancel all position items on a order. Note, only position items in the state PROCESSABLE or CONFIRMED get changed. All other position items get not changed
[**confirmPartnerOrders**](OrdersApi.md#confirmpartnerorders) | **POST** /orders/{salesOrderId}/confirmation | Confirm all position items on an order. Note, only position items in the state PROCESSABLE get changed. All other position items get not changed
[**findPartnerOrders**](OrdersApi.md#findpartnerorders) | **GET** /orders | Get a list of orders which can be filtered on fulfillmentStatus.
[**getPartnerOrderBySalesOrderId**](OrdersApi.md#getpartnerorderbysalesorderid) | **GET** /orders/{salesOrderId} | Get a single order via Sales Order Id

# **cancelPartnerOrders**
> cancelPartnerOrders($sales_order_id)

Cancel all position items on a order. Note, only position items in the state PROCESSABLE or CONFIRMED get changed. All other position items get not changed

Cancels a single salesorder

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new EzzeSiftuz\OrdersV2\Api\OrdersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$sales_order_id = array("sales_order_id_example"); // string[] | 

try {
    $apiInstance->cancelPartnerOrders($sales_order_id);
} catch (Exception $e) {
    echo 'Exception when calling OrdersApi->cancelPartnerOrders: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **sales_order_id** | [**string[]**](../Model/string.md)|  |

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **confirmPartnerOrders**
> confirmPartnerOrders($sales_order_id)

Confirm all position items on an order. Note, only position items in the state PROCESSABLE get changed. All other position items get not changed

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new EzzeSiftuz\OrdersV2\Api\OrdersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$sales_order_id = array("sales_order_id_example"); // string[] | 

try {
    $apiInstance->confirmPartnerOrders($sales_order_id);
} catch (Exception $e) {
    echo 'Exception when calling OrdersApi->confirmPartnerOrders: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **sales_order_id** | [**string[]**](../Model/string.md)|  |

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **findPartnerOrders**
> \EzzeSiftuz\OrdersV2\Model\PartnerOrderList findPartnerOrders($from_date, $fulfillment_status, $limit, $order_direction, $order_column_type, $mode, $nextcursor, $search_term)

Get a list of orders which can be filtered on fulfillmentStatus.

The orders will be sorted on orderDate from oldest to newest. Additionally we provide cursor based pagination via next link. This endpoint is limited to at max 128 results. Note: It can happen, if orders are created in the same millisecond, that you will receive the same partner twice on two successive pages.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new EzzeSiftuz\OrdersV2\Api\OrdersApi(
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
    echo 'Exception when calling OrdersApi->findPartnerOrders: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **from_date** | **\DateTime**| Defines, which minimum lifecycle change date the returned order should have | [optional]
 **fulfillment_status** | [**string[]**](../Model/string.md)| Defines, which minimum state the returned orders should have.&lt;br&gt;If ANNOUNCED is given, all orders, which have at least one position in ANNOUNCED state are returned.&lt;br&gt;If PROCESSABLE is given, all orders, which have at least one position in PROCESSABLE state and none in ANNOUNCED state are returned.&lt;br&gt;If CONFIRMED is given, all orders, which have at least one position in CONFIRMED state and none in either ANNOUNCED or PROCESSABLE state are returned.&lt;br&gt;If SENT is given, all orders, which have at least one position in SENT state and none in either ANNOUNCED or PROCESSABLE or CONFIRMED state are returned.&lt;br&gt;If RETURNED is given, all orders, which have at least one position in RETURNED state and none in either ANNOUNCED or PROCESSABLE or CONFIRMED or SENT state are returned.&lt;br&gt;If CANCELLED_BY_PARTNER is given, all orders, which have at least one position in CANCELLED_BY_PARTNER state are returned.&lt;br&gt;If CANCELLED_BY_MARKETPLACE is given, all orders, which have at least one position in CANCELLED_BY_MARKETPLACE state are returned.&lt;br&gt;If none is provided, all status will be returned.&lt;br&gt;Several values can be passed via request param array, when multiple values passed, search result will be combination of multiple fulfillmentStatuses - no duplicates will appear.&lt;br&gt;Example: ?fulfillmentStatus&#x3D;PROCESSABLE,CONFIRMED&amp;fulfillmentStatus&#x3D;CANCELLED_BY_MARKETPLACE - will return orders in these 3 fulfillmentStatuses.&lt;br&gt;Alternatively, mode can be passed for a different search type. BUCKET/AT_LEAST_ONE, where BUCKET is default behaviour explained above and AT_LEAST_ONE checks if there is at least 1 position item with passed fulfillmentStatus/fulfillmentStatuses. | [optional]
 **limit** | **int**| limit | [optional]
 **order_direction** | **string**| Ordering direction ASC/DESC | [optional]
 **order_column_type** | **string**| Column by which to order partnerOrders | [optional]
 **mode** | **string**| Mode for type of search, default mode is bucket | [optional]
 **nextcursor** | **string**| For paging request this cursor is required. If a next cursor is provided, the only other request parameter being considered is &#x27;limit&#x27;. | [optional]
 **search_term** | **string**| Partial Text Search | [optional]

### Return type

[**\EzzeSiftuz\OrdersV2\Model\PartnerOrderList**](../Model/PartnerOrderList.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getPartnerOrderBySalesOrderId**
> \EzzeSiftuz\OrdersV2\Model\PartnerOrder getPartnerOrderBySalesOrderId($sales_order_id)

Get a single order via Sales Order Id

Returns a single salesorder

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new EzzeSiftuz\OrdersV2\Api\OrdersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$sales_order_id = "sales_order_id_example"; // string | 

try {
    $result = $apiInstance->getPartnerOrderBySalesOrderId($sales_order_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrdersApi->getPartnerOrderBySalesOrderId: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **sales_order_id** | **string**|  |

### Return type

[**\EzzeSiftuz\OrdersV2\Model\PartnerOrder**](../Model/PartnerOrder.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

