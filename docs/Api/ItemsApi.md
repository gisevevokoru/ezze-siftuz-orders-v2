# EzzeSiftuz\OrdersV2\ItemsApi

All URIs are relative to *https://live.api.otto.market/v2*

Method | HTTP request | Description
------------- | ------------- | -------------
[**cancelPartnerOrderPositionItems**](ItemsApi.md#cancelpartnerorderpositionitems) | **POST** /orders/{salesOrderId}/items/{positionItemId}/cancellation | Cancel a single position item
[**confirmPartnerOrderPositionItems**](ItemsApi.md#confirmpartnerorderpositionitems) | **POST** /orders/{salesOrderId}/items/{positionItemId}/confirmation | Confirm a single position item

# **cancelPartnerOrderPositionItems**
> cancelPartnerOrderPositionItems($sales_order_id, $position_item_id)

Cancel a single position item

Cancel a single position item

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new EzzeSiftuz\OrdersV2\Api\ItemsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$sales_order_id = "sales_order_id_example"; // string | 
$position_item_id = array("position_item_id_example"); // string[] | 

try {
    $apiInstance->cancelPartnerOrderPositionItems($sales_order_id, $position_item_id);
} catch (Exception $e) {
    echo 'Exception when calling ItemsApi->cancelPartnerOrderPositionItems: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **sales_order_id** | **string**|  |
 **position_item_id** | [**string[]**](../Model/string.md)|  |

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **confirmPartnerOrderPositionItems**
> confirmPartnerOrderPositionItems($sales_order_id, $position_item_id)

Confirm a single position item

Confirm a single position item

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new EzzeSiftuz\OrdersV2\Api\ItemsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$sales_order_id = "sales_order_id_example"; // string | 
$position_item_id = array("position_item_id_example"); // string[] | 

try {
    $apiInstance->confirmPartnerOrderPositionItems($sales_order_id, $position_item_id);
} catch (Exception $e) {
    echo 'Exception when calling ItemsApi->confirmPartnerOrderPositionItems: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **sales_order_id** | **string**|  |
 **position_item_id** | [**string[]**](../Model/string.md)|  |

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

