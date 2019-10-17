## 1、接口描述  
服务接口：(oSelCusAccount)查询客户账户  
接口描述：xxxxx  
请求说明：POST https://epeis.com/Service/V1/oSelCusAccount  
  
## 2、服务接口请求参数  
#### 2.1、请求参数报文示例  
~~~  
{
	"SYS_HEAD":	{
		"CHANNEL_DID":	"",
		"DYNAMIC_KEY":	"",
		"REGISTER_DID":	""
	},
	"CUS_ACCOUNT":	[{
			"CERTIFICATES_INFO":	"",
			"MOBILE_PHONE_INFO":	"",
			"ACC_CERT_INFO":	"",
			"CUSTOMER_NAME":	"",
			"ATTESTATION_TYPE":	""
		}]
}  
~~~  
#### 2.2、请求参数说明  
参数SYS_HEAD，类型：object  
  
| 参数 | 必选 | 类型 | 描述 |  
| :----------------- | :----: | :-------- | :---------------- |  
| CHANNEL_DID | 是 | String | 16字符渠道号，请与平台运营服务中心联系 |  
| DYNAMIC_KEY | 是 | String | 动态请求密钥，请与平台运营服务中心联系 |  
| REGISTER_DID      |  是  | String   | 16位注册ID，必须实名 |  
  
参数CUS_ACCOUNT，类型：Array  
  
| 参数              | 必选 | 类型     | 描述             |  
| :----------------- | :----: | :-------- | :---------------- |  
| CERTIFICATES_INFO |  否  | String   | xxxxx |  
| MOBILE_PHONE_INFO |  否  | String   | xxxxx |  
| ACC_CERT_INFO |  否  | String   | xxxxx |  
| CUSTOMER_NAME |  否  | String   | xxxxx |  
| ATTESTATION_TYPE |  否  | String   | xxxxx |  
  
说明：xxxxx  
  
## 3、服务接口响应参数  
#### 3.1、响应参数报文示例  
~~~  
{
	"CODE":	0,
	"MESSAGE":	"",
	"DATA":	{
		"CUS_ACCOUNT":	[{
				"CUSTOMER_DID":	"",
				"CUSTOMER_NAME":	""
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
  
参数DATA，类型：object 本服务接口响应数据说明如下：  
参数CUS_ACCOUNT，类型：object  
  

| 参数              | 必选 | 类型     | 描述             |  
| :----------------- | :----: | :-------- | :---------------- |  
| CUSTOMER_DID |  是  | String   | xxxxx |  
| CUSTOMER_NAME |  是  | String   | xxxxx |  
  
说明：xxxxx  
## 4、服务接口说明  
xxxxxxx  