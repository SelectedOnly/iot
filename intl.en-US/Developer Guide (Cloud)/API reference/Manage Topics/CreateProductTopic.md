# CreateProductTopic {#reference_ilx_vrz_wdb .reference}

Call this operation to create a topic category for a specified product.

## Limits {#section_uy5_vyt_xdb .section}

A product can have up to 50 custom topic categories.

## Request parameters {#section_tvj_zyt_xdb .section}

|Parameter|Type|Required|Description|
|:--------|:---|:-------|:----------|
|Action|String|Yes|The operation that you want to perform. Set the value to CreateProductTopic.|
|ProductKey|String|Yes|The unique identifier of the product for which you want to create a topic category.|
|TopicShortName|String|Yes| The custom category hierarchy in the topic category. By default, a topic category contains two system defined category hierarchies: productKey and $\{deviceName\}. Forward slashes \(/\) are used to delimit the topic hierarchies. The format of a topic category is `productKey/$\{deviceName\}/topicShortName`.

 **Note:** The name of each category hierarchy can contain English letters, digits, and underscores \(\_\), and cannot be empty.

 |
|Operation|String|Yes| Operation permissions of devices on the topic category. Value options:

 SUB: Subscribe. Devices can subscribe to the topics of this category.

 PUB: Publish. Devices can publish messages using the topics of this category.

 ALL: Subscribe and publish. Devices can subscribe to and publish messages to the topics of this category.

 |
|Desc|String|No|The description of the topic category. You can enter a description with up to 100 characters.|
|Common Request Parameters|-|Yes|See [Common parameters](intl.en-US/Developer Guide (Cloud)/API reference/Common parameters.md#).|

## Response parameters {#section_hn2_nb5_xdb .section}

|Parameter|Type|Description|
|:--------|:---|:----------|
|RequestId|String|The globally unique ID generated by Alibaba Cloud for the request.|
|Success|Boolean|Indicates whether the call is successful. A value of true indicates that the call is successful. A value of false indicates that the call has failed.|
|ErrorMessage|String|The error message returned when the call fails.|
|Code|String|The error code returned when the call fails. For more information about error codes, see [Error codes](intl.en-US/Developer Guide (Cloud)/API reference/Error codes.md#).|
|TopicId|Long| The topic identifier that is generated by IoT Platform for the created topic category when the call is successful.

 **Note:** Save the information for future reference. You need to provide the topic identifier when calling the operation related to the topic category.

 |

## Examples {#section_uqv_wb5_xdb .section}

**Request example**

```
https://iot.cn-shanghai.aliyuncs.com/?Action=CreateProductTopic
&ProductKey=al*********
&TopicShortName=submit
&Operation=PUB
&Desc=submit a test topic
&Public Request Parameters
```

**Response example**

```
{
    "RequestId":"FCC27691-9151-4B93-9622-9C90F30542EC",
    "Success":true,
    "TopicId":10000
}
```
