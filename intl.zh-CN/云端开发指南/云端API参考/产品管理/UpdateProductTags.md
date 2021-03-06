# UpdateProductTags {#reference_kw5_zrk_3gb .reference}

调用该接口更新产品标签。

## 限制说明 {#section_tx4_csk_3gb .section}

单次调用该接口最多可更新10个标签。

## 请求参数 {#section_pqr_fsk_3gb .section}

|名称|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|要执行的操作。取值UpdateProductTags。|
|ProductKey|String|是|产品Key，物联网平台为产品颁发的唯一标识。|
|ProductTags|List<String\>|是|要更新的标签。标签包括TagKey和TagValue，分别对应标签的key和value。请参见下表[ProductTag](#)。**说明：** 

-   传入标签的TagKey不能重复。
-   传入标签的TagKey必须是已存在的标签key。

|
|公共请求参数|-|是|请参见[公共参数](intl.zh-CN/云端开发指南/云端API参考/公共参数.md#)。|

|名称|类型|是否必需|描述|
|:-|:-|:---|:-|
|TagKey|String|是|产品标签键\(key\)。|
|TagValue|String|是|产品标签值\(value\)。|

## 返回参数 {#section_hwv_5kk_3gb .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|阿里云为该请求生成的唯一标识符。|
|Success|Boolean|表示是否调用成功。true表示调用成功，false表示调用失败。|
|ErrorMessage|String|调用失败时，返回的出错信息。|
|Code|String|调用失败时，返回的错误码。错误码详情，请参见[错误码](intl.zh-CN/云端开发指南/云端API参考/错误码.md#)。|
|InvalidProductTags|List<String\>|调用失败时，返回不合法的产品标签列表。|

## 示例 {#section_jyb_zqk_3gb .section}

**请求示例**

```
https://iot.cn-shanghai.aliyuncs.com/&Action=UpdateProductTags
&ProductKey=a1h7knJdld1
&ProductTag.1.TagKey=first
&ProductTag.1.TagValue=value1
&ProductTag.2.TagKey=second
&ProductTag.2.TagValue=value2
&公共请求参数
```

**返回示例**

JSON格式

```
{
  "RequestId": "92586B4B-FF78-494A-A22C-368E4293FBB7",
  "Success": true
}
```

XML格式

```
<UpdateProductTagsResponse>
    <RequestId>57b144cf-09fc-4916-a272-a62902d5b207</RequestId>
    <Success>true</Success>
</UpdateProductTagsResponse>
```

