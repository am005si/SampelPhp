# OpenAPI\Client\AddressValidationApi

All URIs are relative to *https://api-qa.pitneybowes.com/shippingservices*

Method | HTTP request | Description
------------- | ------------- | -------------
[**verifyAddress**](AddressValidationApi.md#verifyAddress) | **POST** /v1/addresses/verify | Address validation
[**verifySuggest**](AddressValidationApi.md#verifySuggest) | **POST** /v1/addresses/verify-suggest | Address Suggestion



## verifyAddress

> \OpenAPI\Client\Model\Address verifyAddress($accept_language, $address, $x_pb_unified_error_structure, $minimal_address_validation)

Address validation

Address validation verifies and cleanses postal addresses within the United States to help ensure packages are rated accurately and shipments arrive at their final destinations on time.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: oAuth2ClientCredentials
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new OpenAPI\Client\Api\AddressValidationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$accept_language = en-US; // string | This HTTP header advertises which languages the client is able to understand, and which locale variant is preferred.
$address = new \OpenAPI\Client\Model\Address(); // \OpenAPI\Client\Model\Address | Address object that needs to be validated.
$x_pb_unified_error_structure = true; // string | Set this to true to use the standard [error object](https://shipping.pitneybowes.com/reference/error-object.html#standard-error-object) if an error occurs.
$minimal_address_validation = True; // bool | When set to true, the complete address (delivery line and last line) is validated but only the last line (city, state, and postal code) would be changed by the validation check.

try {
    $result = $apiInstance->verifyAddress($accept_language, $address, $x_pb_unified_error_structure, $minimal_address_validation);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AddressValidationApi->verifyAddress: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **accept_language** | **string**| This HTTP header advertises which languages the client is able to understand, and which locale variant is preferred. | [default to &#39;en-US&#39;]
 **address** | [**\OpenAPI\Client\Model\Address**](../Model/Address.md)| Address object that needs to be validated. |
 **x_pb_unified_error_structure** | **string**| Set this to true to use the standard [error object](https://shipping.pitneybowes.com/reference/error-object.html#standard-error-object) if an error occurs. | [optional] [default to &#39;true&#39;]
 **minimal_address_validation** | **bool**| When set to true, the complete address (delivery line and last line) is validated but only the last line (city, state, and postal code) would be changed by the validation check. | [optional]

### Return type

[**\OpenAPI\Client\Model\Address**](../Model/Address.md)

### Authorization

[oAuth2ClientCredentials](../../README.md#oAuth2ClientCredentials)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)


## verifySuggest

> \OpenAPI\Client\Model\AddressSuggestionResponse verifySuggest($accept_language, $return_suggestions, $address, $x_pb_unified_error_structure)

Address Suggestion

This operation returns suggested addresses. Use this if the [Address Validation API](https://shipping.pitneybowes.com/api/post-address-verify.html) call has returned an error.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: oAuth2ClientCredentials
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new OpenAPI\Client\Api\AddressValidationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$accept_language = en-US; // string | This HTTP header advertises which languages the client is able to understand, and which locale variant is preferred.
$return_suggestions = 'true'; // string | To return suggested addresses, set this to true.
$address = new \OpenAPI\Client\Model\Address(); // \OpenAPI\Client\Model\Address | Address object that needs to be validated.
$x_pb_unified_error_structure = true; // string | Set this to true to use the standard [error object](https://shipping.pitneybowes.com/reference/error-object.html#standard-error-object) if an error occurs.

try {
    $result = $apiInstance->verifySuggest($accept_language, $return_suggestions, $address, $x_pb_unified_error_structure);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AddressValidationApi->verifySuggest: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **accept_language** | **string**| This HTTP header advertises which languages the client is able to understand, and which locale variant is preferred. | [default to &#39;en-US&#39;]
 **return_suggestions** | **string**| To return suggested addresses, set this to true. | [default to &#39;true&#39;]
 **address** | [**\OpenAPI\Client\Model\Address**](../Model/Address.md)| Address object that needs to be validated. |
 **x_pb_unified_error_structure** | **string**| Set this to true to use the standard [error object](https://shipping.pitneybowes.com/reference/error-object.html#standard-error-object) if an error occurs. | [optional] [default to &#39;true&#39;]

### Return type

[**\OpenAPI\Client\Model\AddressSuggestionResponse**](../Model/AddressSuggestionResponse.md)

### Authorization

[oAuth2ClientCredentials](../../README.md#oAuth2ClientCredentials)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)

