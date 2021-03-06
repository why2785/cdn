# DescribeDomainRealTimeByteHitRateData {#reference_icl_cps_vdb .reference}

获取域名1分钟粒度字节命中率数据。

-   可以查询7天内的数据， 单次查询StartTime和EndTime跨度不能超过24小时。
-   如果StartTime和EndTime均未指定， 默认返回当前时间起一小时内的数据。

**说明：** 由于存在多域名合并存储的情况，可能会导致命中率数据不准确，具体情况以配置为准。

## 请求参数 {#section_yh3_pps_vdb .section}

|参数|类型|是否必选|示例值|描述|
|Action|String|是|DescribeDomainRealTimeByteHitRateData|系统规定参数。取值：DescribeDomainRealTimeByteHitRateData|
|DomainName|String|是|test.test.com|加速域名。|
|EndTime|String|否|2016-10-20T04:00:00Z| 结束时间。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   例如：2016-10-20T04:00:00Z。
-   不填默认查询从StartTime起一小时内的数据。

 |
|StartTime|String|否|2016-10-20T04:00:00Z| 起始时间。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   例如：2016-10-20T04:00:00Z。
-   不填默认查询从EndTime起一小时内的数据。

 |
|Version|String|否|2014-11-11|API版本。|

## 返回参数 {#section_fcl_5ps_vdb .section}

|参数|类型|示例值|描述|
|RequestId|String|70A26B11-3673-479C-AEA8-E03FC5D3496D|请求ID。|
|Data| | |返回数据。|
|  └ByteHitRate|Float|0.8956940476262277|字节命中率数据。|
|  └TimeStamp|String|2016-10-20T04:00:00Z| 数据时间戳。

 -   日期格式按照ISO8601表示法，并使用UTC时间。
-   例如：2016-10-20T04:00:00Z。

 |

## 示例 {#section_uz2_x1n_vdb .section}

**请求示例**

```
https://cdn.aliyuncs.com/?Action=DescribeDomainRealTimeByteHitRateData&DomainName=www.domainname.com&EndTime=2018-01-02T11%3A05%3A37Z公共请求参数
```

**正常返回示例**

-   JSON格式

    ```
    {
        "Data":{
            "ByteHitRateModel":[
                {
                    "ByteHitRate":0.8956940476262277,
                    "TimeStamp":"2018-01-02T11:26:00Z"
                },
                {
                    "ByteHitRate":0.8429129920796812,
                    "TimeStamp":"2018-01-02T11:25:00Z"
                }
            ]
        },
        "RequestId":"70A26B11-3673-479C-AEA8-E03FC5D3496D"
    }
    ```


**异常返回示例**

-   JSON格式

    ```
    {
        "Code":"InternalError",
        "HostId":"cdn.aliyuncs.com",
        "Message":"The request processing has failed due to some unknown error.",
        "RequestId":"16A96B9A-F203-4EC5-8E43-CB92E68F4CD8"
    }
    ```


