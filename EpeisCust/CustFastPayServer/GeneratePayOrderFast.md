## 1、接口描述  
服务接口：(GeneratePayOrderFast)生成快速缴费订单  
接口描述：生成快速缴费订单  
请求说明：POST https://api.epeis.com/Service/v1/GeneratePayOrderFast/  
  
## 2、服务接口请求参数  
#### 2.1、请求参数报文示例  
~~~  
{
	"SYS_HEAD":	{
		"CHANNEL_DID":	"",
		"DYNAMIC_KEY":	"",
		"REGISTER_DID":	""
	},
	"INOUT_ORDER":	{
		"PAY_CHARGE_DID":	"",
		"PAID_IN_AMOUNT":	0
	}
}  
~~~  
#### 2.2、请求参数说明  
参数：SYS_HEAD，类型：object  
  
| 参数 | 必选 | 类型 | 长度 | 精度 | 描述 |  
| :----------------- | :----: | :-------- | :----: | :----: | :---------------- |  
| CHANNEL_DID | 是 | String | 16 | 0 | 16字符渠道号，请与平台运营服务中心联系 |  
| DYNAMIC_KEY | 是 | String | 64 | 0 | 动态请求密钥，请与平台运营服务中心联系 |  
| REGISTER_DID      |  是  | String   | 16 | 0 | 16位注册ID，可不实名 |  
  
参数：INOUT_ORDER，类型：object  
  
| 参数              | 必选 | 类型     | 长度 | 精度 | 描述             |  
| :----------------- | :----: | :-------- | :----: | :----: | :---------------- |  
| PAY_CHARGE_DID |  是  | String   | 16 | 0 | 16个字符，客户编号或结算户编号 |  
| PAID_IN_AMOUNT |  是  | Number   | 16 | 2 | 实缴总计金额 |  
  
说明：订单信息  
  
## 3、服务接口响应参数  
#### 3.1、响应参数报文示例  
~~~  
{
	"CODE":	0,
	"MESSAGE":	"",
	"DATA":	{
		"INOUT_ORDER":	[{
				"OPERATION_DATE":	0,
				"SERIAL_DID":	""
			}]
	}
}  
~~~  
#### 3.2、响应参数说明  
  
| 参数              | 必选 | 类型     | 描述             |  
| :----------------- | :----: | :-------- | :---------------- |  
| CODE | 是 | Number | 响应代码，0为成功 |  
| MESSAGE | 是 | String | 响应信息 |  
| DATA | 是 | Object | 响应数据 |  
  
参数：DATA，类型：object 本服务接口响应数据说明如下：  
  
参数：INOUT_ORDER，类型：Array  
  

| 参数              | 必选 | 类型     | 描述             |  
| :----------------- | :----: | :-------- | :---------------- |  
| OPERATION_DATE |  是  | Number   | 订单日期 |  
| SERIAL_DID |  是  | String   | 订单业务流水号 |  
  
说明：订单信息  
## 4、服务接口说明  
说明：无  
