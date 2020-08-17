#中控服务端API说明

### BASE_URL=http://47.240.44.22:8090

### API返回格式说明

```json
{
  "code": "返回代码",
  "data": "数据",
  "msg": "信息提醒"
}
```

### API返回代码说明

| Code | Type | Description |
| ---- | ---- | ----------- |
| 20000 | STRING | 正常 |
| 30000 | STRING | 数据库错误 |
| 30001 | STRING | 数据查询错误 |
| 40001 | STRING | 未经授权的错误 |
| 40002 | STRING | TOKEN错误 |
| 40003 | STRING | TOKEN过期 |
| 40004 | STRING | 密码错误 |
| 50000 | STRING | 参数错误 |
| 50001 | STRING | 上传错误 |
| 50003 | STRING | 推送错误 |
| 50004 | STRING | WEBSOCKET错误 |

## 参考交易所类API
### 1.更新或添加参考交易所类
Parameters:

| Name | Type | Example | Description  |
| ---- | ---- | -------- | ------------ |
| name | STRING | okex | 参考交易所名|
| params_description | STRING | {...} | 参数描述 |
```
POST /refer-exchange-class
```
Response:
```json
{
	"code": 20000,
	"msg": "存储成功",
	"data": {}
}
```

### 2.删除参考交易所类
```
DELETE /refer-exchange-class/{refer_exchange_class_id}
```
Response:
```json
{
	"code": 20000,
	"msg": "删除成功",
	"data": {}
}
```

### 3.获取所有参考交易所类
```
GET /refer-exchange-classes
```
Response:
```json
{
	"code": 20000,
	"msg": "查询成功",
	"data": [
                    {
                        "CreatedAt": "2020-07-02T15:43:03+08:00",
                        "UpdatedAt": "2020-07-02T15:43:03+08:00",
                        "DeletedAt": null,
                        "ID": 4,
                        "name": "okex_v3",
                        "params_description": "[{\"name\":\"apiKey\",\"nick_name\":\"apiKey\",\"default\":\"\",\"show_condition\":\"\",\"type\":\"STRING\",\"sub_type\":\"\",\"sub_params\":\"\",\"description\":\"交易所申请的apiKey\"},{\"name\":\"secret\",\"nick_name\":\"secret\",\"default\":\"\",\"show_condition\":\"\",\"type\":\"STRING\",\"sub_type\":\"\",\"sub_params\":\"\",\"description\":\"交易所申请的secret\"},{\"name\":\"password\",\"nick_name\":\"password\",\"default\":\"\",\"show_condition\":\"\",\"type\":\"STRING\",\"sub_type\":\"\",\"sub_params\":\"\",\"description\":\"交易所申请的password\"}]"
                    },
                    {
                        "CreatedAt": "2020-07-02T15:43:23+08:00",
                        "UpdatedAt": "2020-07-02T15:43:23+08:00",
                        "DeletedAt": null,
                        "ID": 5,
                        "name": "okex_v1",
                        "params_description": "[{\"name\":\"apiKey\",\"nick_name\":\"apiKey\",\"default\":\"\",\"show_condition\":\"\",\"type\":\"STRING\",\"sub_type\":\"\",\"sub_params\":\"\",\"description\":\"交易所申请的apiKey\"},{\"name\":\"secret\",\"nick_name\":\"secret\",\"default\":\"\",\"show_condition\":\"\",\"type\":\"STRING\",\"sub_type\":\"\",\"sub_params\":\"\",\"description\":\"交易所申请的secret\"}]"
                    }
                ]
}
```

## 参考交易所API
### 1.更新或添加参考交易所
Parameters:

| Name | Type | Example | Description  |
| ---- | ---- | -------- | ------------ |
| name | STRING | okex | 参考交易所名|
| params | STRING | {...} | 参数|
| class_id | STRING | 1 | 参考交易所类id |
```
POST /refer-exchange
```
Response:
```json
{
	"code": 20000,
	"msg": "存储成功",
	"data": {}
}
```

### 2.删除参考交易所
```
DELETE /refer-exchange/{refer_exchange_id}
```
Response:
```json
{
	"code": 20000,
	"msg": "删除成功",
	"data": {}
}
```

### 3.获取所有参考交易所
```
GET /refer-exchanges
```
Response:
```json
{
    "code": 20000,
    "data": [
        {
            "CreatedAt": "2020-07-02T15:52:44+08:00",
            "UpdatedAt": "2020-07-02T15:52:44+08:00",
            "DeletedAt": null,
            "ID": 4,
            "name": "okex_v1_object",
            "class_id": 5,
            "params": "{\"apiKey\": \"hoo6666\",\"secret\": \"hoo9999\"}"
        }
    ],
    "msg": "查询成功"
}
```

## 做市交易所API
### 1.更新或添加做市交易所
Parameters:

| Name | Type | Example | Description  |
| ---- | ---- | -------- | ------------ |
| name | STRING | hoo | 名称 |
| symbol | STRING | BTC-USDT | 交易对 |
| api_key | STRING | hoo6666666 | api_key |
| secret | STRING | hoo9999999 | secret |
| price_precision | STRING | 4 | 价格精度 |
| volume_precision | STRING | 4 | 数量精度 |

```
POST /exchange
```
Response:
```json
{
	"code": 20000,
	"msg": "存储成功",
	"data": {}
}
```

### 2.删除做市交易所
```
DELETE /exchange/{id}
```
Response:
```json
{
	"code": 20000,
	"msg": "删除成功",
	"data": {}
}
```

### 3.获取所有做市交易所
```
GET /exchanges
```
Response:
```json
{
    "code": 20000,
    "data": [
        {
            "CreatedAt": "2020-06-19T16:24:28+08:00",
            "UpdatedAt": "2020-06-19T16:24:28+08:00",
            "DeletedAt": null,
            "ID": 2,
            "name": "测试交易所账户2",
            "symbol": "BTC-USDT",
            "api_key": "dsgdsge9349tu9",
            "secret": "kvsdvso88888",
            "price_precision": 8,
            "volume_precision": 8
        }
    ],
    "msg": "查询成功"
}
```

## 策略类API
###1.更新或添加策略类
Parameters:
| Name | Type | Example | Description  |
| ---- | ---- | -------- | ------------ |
| name | STRING | 测试策略类 | 名称 |
| application_name | STRING | testStrategyClass | 应用程序名 |
| params_description | STRING | {...} | 参数描述 |
```
POST /strategt-class
```
Response:
```json
{
	"code": 20000,
	"msg": "存储成功",
	"data": {}
}
```
###2.删除策略类
```
DElETE /strategt-class/{class_id}
```
Response:
```json
{
	"code": 20000,
	"msg": "删除成功",
	"data": {}
}
```
###3.获取所有策略类
```
GET /strategt-classes
```
Response:
```json
{
	"code": 20000,
	"msg": "查询成功",
	"data": {}
}
```

## 策略实例API  
###1.更新或添加策略实例
Parameters:

| Name | Type | Example | Description  |
| ---- | ---- | -------- | ------------ |
| name | STRING | 测试策略 | 名称 |
| class_id | STRING | 1 | 策略类id |
| client_id | STRING | 1 | 客户端id |
| params | STRING | {...} | 参数 |
```
POST /strategy-object
```
Response:
```json
{
	"code": 20000,
	"msg": "存储成功",
	"data": {}
}
```
###2.删除策略实例
```
DELETE /strategy-object/{strategy_id}
```
Response:
```json
{
	"code": 20000,
	"msg": "删除成功",
	"data": {}
}
```
###3.获取单个策略实例
```
GET /strategy-object/{strategy_id}
```
Response:
```json
{
    "code": 20000,
    "data": {
        "CreatedAt": "2020-07-02T15:36:11+08:00",
        "UpdatedAt": "2020-07-02T15:36:11+08:00",
        "DeletedAt": null,
        "ID": 11,
        "name": "BTC-USDT基础铺单策略6",
        "class_id": 5,
        "client_id": 2,
        "params": "{\"buyCount\":100,\"buyPrice\":9300,\"sellCount\":100,\"sellPrice\":9300}"
    },
    "msg": "查询成功"
}
```
###4.获取所有策略实例
```
GET /strategy-objects
```
Response:
```json
{
    "code": 20000,
    "data": [
        {
            "CreatedAt": "2020-07-02T15:32:43+08:00",
            "UpdatedAt": "2020-07-02T15:32:43+08:00",
            "DeletedAt": null,
            "ID": 6,
            "name": "BTC-USDT基础铺单策略",
            "class_id": 5,
            "client_id": 1,
            "params": "{\"buyCount\":100,\"buyPrice\":9300,\"sellCount\":100,\"sellPrice\":9300}"
        }
    ],
    "msg": "查询成功"
}
```
###5.获取单个客户端策略实例
```
GET /strategy-objects/{client_id}
```
Response:
```json
{
    "code": 20000,
    "data": [
        {
            "CreatedAt": "2020-07-02T15:32:43+08:00",
            "UpdatedAt": "2020-07-02T15:32:43+08:00",
            "DeletedAt": null,
            "ID": 6,
            "name": "BTC-USDT基础铺单策略",
            "class_id": 5,
            "client_id": 1,
            "params": "{\"buyCount\":100,\"buyPrice\":9300,\"sellCount\":100,\"sellPrice\":9300}"
        }
    ],
    "msg": "查询成功"
}
```
##客户端API
###1.更新或添加客户端
Parameters:

| Name | Type | Example | Description  |
| ---- | ---- | -------- | ------------ |
| name | STRING | 测试客户端 | 名称 |
| public_host | STRING | 1 | 公网ip |
| private_host | STRING | 1 | 内网ip |
| port | STRING |6666 | 端口 |
```
POST /client
```
Response:
```json
{
	"code": 20000,
	"msg": "查询成功",
	"data": {}
}
```
###2.删除客户端
```
DELETE /client/{client_id}
```
Response:
```json
{
	"code": 20000,
	"msg": "删除成功",
	"data": {}
}
```
###3.通过公网ip和内网ip获取客户端id
Parameters:

| Name | Type | Example | Description  |
| ---- | ---- | -------- | ------------ |
| public_host | STRING | 34.423.423.99 | 公网ip |
| private_host | STRING | 127.0.0.1 | 内网ip |
```
GET /client
```
Response:
```json
{
    "code": 20000,
    "data": "{id:1}",
    "msg": "查询成功"
}
```
###4.获取所有客户端
```
GET /clients
```
Response:
```json
{
    "code": 20000,
    "data": [
        {
            "CreatedAt": "2020-07-02T16:09:09+08:00",
            "UpdatedAt": "2020-07-02T16:11:39+08:00",
            "DeletedAt": null,
            "ID": 1,
            "name": "测试客户端",
            "public_host": "66.66.66.66",
            "private_host": "127.0.0.1",
            "port": "8090"
        }
    ],
    "msg": "查询成功"
}
```

## 策略心跳API
###1.更新或添加策略心跳
Parameters:

| Name | Type | Example | Description  |
| ---- | ---- | -------- | ------------ |
| strategy_id | STRING | 1 | 策略实例id |
| status | STRING | 1 | 策略实例状态 |
```
POST /strategy-heart-beat
```
Response:
```json
{
	"code": 20000,
	"msg": "查询成功",
	"data": {}
}
```
###2.删除策略心跳
```
DELETE /strategy-heart-beat/{strategy_id}
```
Response:
```json
{
	"code": 20000,
	"msg": "删除成功",
	"data": {}
}
```
###3.获取所有策略心跳
```
GET /strategy-heart-beats
```
Response:
```json
{
    "code": 20000,
    "data": [
        {
            "CreatedAt": "2020-07-02T16:38:50+08:00",
            "UpdatedAt": "2020-07-02T16:38:50+08:00",
            "DeletedAt": null,
            "ID": 1,
            "strategy_id": 6,
            "status": 1
        }
    ],
    "msg": "查询成功"
}
```
## 客户端心跳API
###1.更新或添加客户端心跳
Parameters:

| Name | Type | Example | Description  |
| ---- | ---- | -------- | ------------ |
| client_id | STRING | 1 | 策略实例id |
| cpu_usage | STRING | 1 | cpu使用率 |
| mem_usage | STRING | 1 | 内存使用率 |
| disk_usage | STRING | 1 | 硬盘使用率 |
```
POST /client-heart-beat
```
Response:
```json
{
	"code": 20000,
	"msg": "查询成功",
	"data": {}
}
```
###2.删除客户端心跳
```
DELETE /client-heart-beat/{client_id}
```
Response:
```json
{
	"code": 20000,
	"msg": "删除成功",
	"data": {}
}
```
###3.获取所有客户端心跳
```
GET /client-heart-beats
```
Response:
```json
{
    "code": 20000,
    "data": [
        {
            "CreatedAt": "2020-07-02T16:33:24+08:00",
            "UpdatedAt": "2020-07-02T16:33:24+08:00",
            "DeletedAt": null,
            "ID": 1,
            "client_id": 1,
            "cpu_usage": 0.2,
            "mem_usage": 0.2,
            "disk_usage": 0.3
        }
    ],
    "msg": "查询成功"
}
```

## 策略操作API
###1. 操作策略
Parameters:

| Name | Type | Example | Description  |
| ---- | ---- | -------- | ------------ |
| id | STRING | 1 | 策略id |
| operation | STRING | start | 操作(start/stop) |

```
PUT /strategy-object-control
```
Response:
```json
{
    "code": 20000,
    "data": {},
    "msg": "策略操作成功"
}
```