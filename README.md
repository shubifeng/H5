

# analysis-web swagger（数据平台api）


<a name="overview"></a>
## Overview
全局统一约定：1.时间传输用时间戳类型，2.所有金额一律以分为单位进行处理并返回


### Version information
*Version* : 1.1.0.RELEASE


### Contact information
*Contact* : 舒笔锋，罗灿江


### URI scheme
*Host* : localhost:9063  
*BasePath* : /


### Tags

* 云分销app-商品数据 : Report Ware Controller
* 云分销app-预付款报表 : Report Channel Purchase Controller




<a name="paths"></a>
## Paths

<a name="orderchartusingget"></a>
### 预付款提货汇总柱状图
```
GET /reports/channelPurchase/orderChart
```


#### Parameters

|Type|Name|Description|Schema|Default|
|---|---|---|---|---|
|**Query**|**beginTime**  <br>*required*|beginTime|integer (int64)||
|**Query**|**endTime**  <br>*required*|endTime|integer (int64)||
|**Query**|**orderType**  <br>*optional*|预付款订单类型：YUN_MI (1云米产品提货), XIAO_MI (2小米生态链产品提货), MATERIAL (3物料提货)|integer (int32)|`1`|
|**Query**|**timeType**  <br>*required*|timeType可选值: day(d按天,默认),month(m按月),quart(q按季),year(y按年). 如 timeType, beginTime, endTime组合使用, beginTime和endTime为时间戳格式|enum (day, month, quart, year)||
|**Query**|**token**  <br>*required*|用户会话token|string||


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|[接口返回对象的结构«渠道预付款统计汇总»](#c34275553d01a00d789cca1b31932b12)|
|**401**|Unauthorized|No Content|
|**403**|Forbidden|No Content|
|**404**|Not Found|No Content|


#### Consumes

* `application/json`


#### Produces

* `*/*`


#### Tags

* 云分销app-预付款报表


<a name="orderchartdetailusingget"></a>
### 预付款提货报表明细
```
GET /reports/channelPurchase/orderChartDetail
```


#### Parameters

|Type|Name|Description|Schema|Default|
|---|---|---|---|---|
|**Query**|**beginTime**  <br>*required*|beginTime|integer (int64)||
|**Query**|**endTime**  <br>*required*|endTime|integer (int64)||
|**Query**|**orderType**  <br>*optional*|预付款订单类型：YUN_MI (1云米产品提货), XIAO_MI (2小米生态链产品提货), MATERIAL (3物料提货)|integer (int32)|`1`|
|**Query**|**token**  <br>*required*|用户会话token|string||


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|[接口返回对象的结构«List«渠道预付款订单统计详情»»](#c8573487afa1171387ea0a6ca5d85d41)|
|**401**|Unauthorized|No Content|
|**403**|Forbidden|No Content|
|**404**|Not Found|No Content|


#### Consumes

* `application/json`


#### Produces

* `*/*`


#### Tags

* 云分销app-预付款报表


<a name="waressaleslistusingget"></a>
### 商品数据：订单商品的销售量，销售额
```
GET /reports/wares/sales
```


#### Parameters

|Type|Name|Description|Schema|
|---|---|---|---|
|**Query**|**beginTime**  <br>*required*|beginTime|integer (int64)|
|**Query**|**endTime**  <br>*required*|endTime|integer (int64)|
|**Query**|**platformType**  <br>*required*|平台类型：YUN_MI (1云米商城), MI_JIA (2米家商城), TIAN_MAO (3天猫商城), YU_FU_KUAN (4预付款提货)|enum (YUN_MI, MI_JIA, TIAN_MAO, YU_FU_KUAN)|
|**Query**|**timeType**  <br>*required*|timeType可选值: day(d按天,默认),month(m按月),quart(q按季),year(y按年). 如 timeType, beginTime, endTime组合使用, beginTime和endTime为时间戳格式|enum (day, month, quart, year)|
|**Query**|**token**  <br>*required*|用户会话token|string|


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|[接口返回对象的结构«List«某个时间内商品的销售量与销售额»»](#c16b681475f35278c6fd93d55982151b)|
|**401**|Unauthorized|No Content|
|**403**|Forbidden|No Content|
|**404**|Not Found|No Content|


#### Consumes

* `application/json`


#### Produces

* `*/*`


#### Tags

* 云分销app-商品数据


<a name="waressalesdetaillistusingget"></a>
### 商品数据：订单商品的销售量，销售额
```
GET /reports/wares/salesDetail
```


#### Parameters

|Type|Name|Description|Schema|
|---|---|---|---|
|**Query**|**beginTime**  <br>*required*|beginTime|integer (int64)|
|**Query**|**endTime**  <br>*required*|endTime|integer (int64)|
|**Query**|**platformType**  <br>*required*|平台类型：YUN_MI (1云米商城), MI_JIA (2米家商城), TIAN_MAO (3天猫商城), YU_FU_KUAN (4预付款提货)|enum (YUN_MI, MI_JIA, TIAN_MAO, YU_FU_KUAN)|
|**Query**|**timeType**  <br>*required*|timeType可选值: day(d按天,默认),month(m按月),quart(q按季),year(y按年). 如 timeType, beginTime, endTime组合使用, beginTime和endTime为时间戳格式|enum (day, month, quart, year)|
|**Query**|**token**  <br>*required*|用户会话token|string|


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|[接口返回对象的结构«List«某个时间内某一种商品的销售量与销售额»»](#8d1c5d4f8ff9c31a63009992d2829adb)|
|**401**|Unauthorized|No Content|
|**403**|Forbidden|No Content|
|**404**|Not Found|No Content|


#### Consumes

* `application/json`


#### Produces

* `*/*`


#### Tags

* 云分销app-商品数据


<a name="wareprodlistusingget"></a>
### 商品数据：商品的库存量，待发货数
```
GET /reports/wares/stock
```


#### Parameters

|Type|Name|Description|Schema|
|---|---|---|---|
|**Query**|**catalogIds**  <br>*optional*|商品所属类目id：多个以,分割。https://note.youdao.com/share/?token=6E940ACE238B4D39AADA5F67B20C6B04&gid=42130582|string|
|**Query**|**pendingCountRange**  <br>*optional*|待出库范围：10,200 表示（开始值,结束值），或者为空值|string|
|**Query**|**prodName**  <br>*optional*|prodName|string|
|**Query**|**saleStatus**  <br>*optional*|商品在售状态：0预售,1在售|integer (int32)|
|**Query**|**stockCountRange**  <br>*optional*|库存范围：10,200 表示（开始值,结束值），或者为空值|string|
|**Query**|**token**  <br>*required*|用户会话token|string|


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|[接口返回对象的结构«List«商品的存库与待发货数»»](#87a28954a2fc9d6897168a84803d1399)|
|**401**|Unauthorized|No Content|
|**403**|Forbidden|No Content|
|**404**|Not Found|No Content|


#### Consumes

* `application/json`


#### Produces

* `*/*`


#### Tags

* 云分销app-商品数据




<a name="definitions"></a>
## Definitions

<a name="61f16ed3a104d14e18777d63d3d38c53"></a>
### 商品的存库与待发货数

|Name|Description|Schema|
|---|---|---|
|**name**  <br>*optional*|商品名称|string|
|**pending_count**  <br>*optional*|代发货数|integer (int32)|
|**stock**  <br>*optional*|库存数|integer (int32)|
|**type_name**  <br>*optional*|商品类型名称|string|


<a name="87a28954a2fc9d6897168a84803d1399"></a>
### 接口返回对象的结构«List«商品的存库与待发货数»»

|Name|Description|Schema|
|---|---|---|
|**code**  <br>*required*|接口状态码|integer (int32)|
|**desc**  <br>*optional*|接口状态描述|string|
|**result**  <br>*optional*|返回数据对象|< [商品的存库与待发货数](#61f16ed3a104d14e18777d63d3d38c53) > array|
|**timestamp**  <br>*optional*|当出现错误时,该节点值会存在,返回定位时间戳,可用于查日志位置|integer (int64)|


<a name="c16b681475f35278c6fd93d55982151b"></a>
### 接口返回对象的结构«List«某个时间内商品的销售量与销售额»»

|Name|Description|Schema|
|---|---|---|
|**code**  <br>*required*|接口状态码|integer (int32)|
|**desc**  <br>*optional*|接口状态描述|string|
|**result**  <br>*optional*|返回数据对象|< [某个时间内商品的销售量与销售额](#e52e877e04cbe4739038e4a2f3406cc1) > array|
|**timestamp**  <br>*optional*|当出现错误时,该节点值会存在,返回定位时间戳,可用于查日志位置|integer (int64)|


<a name="8d1c5d4f8ff9c31a63009992d2829adb"></a>
### 接口返回对象的结构«List«某个时间内某一种商品的销售量与销售额»»

|Name|Description|Schema|
|---|---|---|
|**code**  <br>*required*|接口状态码|integer (int32)|
|**desc**  <br>*optional*|接口状态描述|string|
|**result**  <br>*optional*|返回数据对象|< [某个时间内某一种商品的销售量与销售额](#900f21f598e484fe615236de8a8e15f3) > array|
|**timestamp**  <br>*optional*|当出现错误时,该节点值会存在,返回定位时间戳,可用于查日志位置|integer (int64)|


<a name="c8573487afa1171387ea0a6ca5d85d41"></a>
### 接口返回对象的结构«List«渠道预付款订单统计详情»»

|Name|Description|Schema|
|---|---|---|
|**code**  <br>*required*|接口状态码|integer (int32)|
|**desc**  <br>*optional*|接口状态描述|string|
|**result**  <br>*optional*|返回数据对象|< [渠道预付款订单统计详情](#760591bfb351570dd3bc1ce434b44ee8) > array|
|**timestamp**  <br>*optional*|当出现错误时,该节点值会存在,返回定位时间戳,可用于查日志位置|integer (int64)|


<a name="c34275553d01a00d789cca1b31932b12"></a>
### 接口返回对象的结构«渠道预付款统计汇总»

|Name|Description|Schema|
|---|---|---|
|**code**  <br>*required*|接口状态码|integer (int32)|
|**desc**  <br>*optional*|接口状态描述|string|
|**result**  <br>*optional*|返回数据对象|[渠道预付款统计汇总](#24667b16b4386ce548d58ba280809d4c)|
|**timestamp**  <br>*optional*|当出现错误时,该节点值会存在,返回定位时间戳,可用于查日志位置|integer (int64)|


<a name="e52e877e04cbe4739038e4a2f3406cc1"></a>
### 某个时间内商品的销售量与销售额

|Name|Description|Schema|
|---|---|---|
|**data_time**  <br>*optional*|x轴时间|string|
|**quantity**  <br>*optional*|y轴商品销售量|string|
|**sales**  <br>*optional*|y轴商品销售额|string|


<a name="900f21f598e484fe615236de8a8e15f3"></a>
### 某个时间内某一种商品的销售量与销售额

|Name|Description|Schema|
|---|---|---|
|**name**  <br>*optional*|商品名称|string|
|**quantity**  <br>*optional*|商品销量|integer (int32)|
|**sales**  <br>*optional*|商品销额|integer (int64)|


<a name="24667b16b4386ce548d58ba280809d4c"></a>
### 渠道预付款统计汇总

|Name|Description|Schema|
|---|---|---|
|**listData**  <br>*optional*|列表数据|< [渠道预付款订单统计列表](#41878b656a79712e08a5e35f45061c92) > array|
|**totalData**  <br>*optional*|汇总数据|[渠道预付款订单统计汇总](#7eb783f397fb6fefbdee52ddcef6613c)|


<a name="41878b656a79712e08a5e35f45061c92"></a>
### 渠道预付款订单统计列表

|Name|Description|Schema|
|---|---|---|
|**dataTime**  <br>*optional*|数据时间|string|
|**orderFee**  <br>*optional*|提货金额|integer (int64)|
|**orderNum**  <br>*optional*|提货订单数|integer (int64)|
|**refundOrderFee**  <br>*optional*|退货退款额|integer (int64)|
|**refundOrderNum**  <br>*optional*|退货退款订单|integer (int64)|


<a name="7eb783f397fb6fefbdee52ddcef6613c"></a>
### 渠道预付款订单统计汇总
ChannelPurchaseOrderResp的数据汇总


|Name|Description|Schema|
|---|---|---|
|**orderFee**  <br>*optional*|提货金额|integer (int64)|
|**orderNum**  <br>*optional*|提货订单数|integer (int64)|
|**refundOrderFee**  <br>*optional*|退货退款额|integer (int64)|
|**refundOrderNum**  <br>*optional*|退货退款订单|integer (int64)|


<a name="760591bfb351570dd3bc1ce434b44ee8"></a>
### 渠道预付款订单统计详情

|Name|Description|Schema|
|---|---|---|
|**channelId**  <br>*optional*|渠道ID|integer (int64)|
|**channelName**  <br>*optional*|门店名称|string|
|**orderFee**  <br>*optional*|提货金额|integer (int64)|
|**orderNum**  <br>*optional*|提货订单数|integer (int64)|
|**productNum**  <br>*optional*|商品数|integer (int64)|
|**rootChannel**  <br>*optional*|城市运营名称|string|
|**secondChannel**  <br>*optional*|经销商名称|string|



