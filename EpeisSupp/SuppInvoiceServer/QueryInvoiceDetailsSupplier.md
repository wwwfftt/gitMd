## 1、接口描述  
服务接口：(QueryInvoiceDetailsSupplier)查询发票明细信息  
接口描述：查询发票明细信息  
请求说明：POST https://api.epeis.com/Service/v1/QueryInvoiceDetailsSupplier/  
  
## 2、服务接口请求参数  
#### 2.1、请求参数报文示例  
~~~  
{
	"SYS_HEAD":	{
		"CHANNEL_DID":	"",
		"DYNAMIC_KEY":	"",
		"REGISTER_DID":	"",
		"ACCOUNT_DID":	""
	},
	"ACC_INVOICE":	{
		"INVOICE_DID":	"",
		"ACCOUNT_MONTH":	0
	}
}  
~~~  
#### 2.2、请求参数说明  
参数：SYS_HEAD，类型：object  
  
| 参数 | 必选 | 类型 | 长度 | 精度 | 描述 |  
| :----------------- | :----: | :-------- | :----: | :----: | :---------------- |  
| CHANNEL_DID | 是 | String | 16 | 0 | 16字符渠道号，请与平台运营服务中心联系 |  
| DYNAMIC_KEY | 是 | String | 64 | 0 | 动态请求密钥，请与平台运营服务中心联系 |  
| REGISTER_DID      |  是  | String   | 16 | 0 | 16位注册ID，必须实名 |  
| ACCOUNT_DID       |  是  | String   | 16 | 0 | 16位账户ID，必须激活 |  
  
参数：ACC_INVOICE，类型：object  
  
| 参数              | 必选 | 类型     | 长度 | 精度 | 描述             |  
| :----------------- | :----: | :-------- | :----: | :----: | :---------------- |  
| INVOICE_DID |  是  | String   | 16 | 0 | 16位字符，发票唯一的ID |  
| ACCOUNT_MONTH |  是  | Number   | 6 | 0 | 账务月份 |  
  
说明：发票信息  
  
## 3、服务接口响应参数  
#### 3.1、响应参数报文示例  
~~~  
{
	"CODE":	0,
	"MESSAGE":	"",
	"DATA":	{
		"ACC_INVOICE":	[{
				"INVOICE_DID":	"",
				"SUPPLIER_NAME":	"",
				"ADMIN_CODE_INFO":	"",
				"ADDRESS":	"",
				"TAX_NUMBER_INFO":	"",
				"TELEPHONE_INFO":	"",
				"BANK_ACCOUNT_INFO":	"",
				"BANK_NAME":	"",
				"CUSTOMER_DID":	"",
				"CUSTOMER_NAME":	"",
				"USER_ACCOUNT_AID":	"",
				"CADMIN_CODE_INFO":	"",
				"CADDRESS":	"",
				"CTAX_NUMBER_INFO":	"",
				"CTELEPHONE_INFO":	"",
				"CBANK_ACCOUNT_INFO":	"",
				"CBANK_NAME":	"",
				"NETWORK_TYPE":	"",
				"ACCOUNT_MONTH":	0,
				"TAX_EXCLUDE_AMOUNT":	0
			}],
		"ACC_INVOICE_DETAIL":	[{
				"INVOICE_DID":	"",
				"COMMODITY_CODE_INFO":	"",
				"GOODSNAME":	"",
				"AMOUNT":	"",
				"PRICE":	0,
				"TAX_INCLUDE_YESNO":	"",
				"VAT_TAX_RATE":	0,
				"SPECIFICATION_INFO":	"",
				"UNIT_INFO":	"",
				"SELF_CODE_INFO":	"",
				"FAVOURED_POLICY_TYPE":	"",
				"ZERO_TAX_RATE_TYPE":	"",
				"DEDUCTED_AMOUNT":	0,
				"TAX_EXCLUDE_AMOUNT":	0,
				"TAX_AMOUNT":	0,
				"TAX_INCLUDE_AMOUNT":	0
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
  
参数：ACC_INVOICE，类型：Array  
  

| 参数              | 必选 | 类型     | 描述             |  
| :----------------- | :----: | :-------- | :---------------- |  
| INVOICE_DID |  是  | String   | 16位字符，发票唯一的ID |  
| SUPPLIER_NAME |  是  | String   | 256个字符,供应商名称 |  
| ADMIN_CODE_INFO |  是  | String   | 20个字符，行政区划统一编码 |  
| ADDRESS |  是  | String   | 128个字符，详细地址 |  
| TAX_NUMBER_INFO |  是  | String   | 30个字符，纳税识别号 |  
| TELEPHONE_INFO |  是  | String   | 20个字符，固定电话 |  
| BANK_ACCOUNT_INFO |  是  | String   | 30个字符，银行账号 |  
| BANK_NAME |  是  | String   | 256个字符，开户行名称 |  
| CUSTOMER_DID |  是  | String   | 16个字符，客户唯一的账号ID |  
| CUSTOMER_NAME |  是  | String   | 256个字符，客户名称 |  
| USER_ACCOUNT_AID |  是  | String   | 16个字符,用户地址唯一ID |  
| CADMIN_CODE_INFO |  是  | String   | 20个字符，行政区划统一编码 |  
| CADDRESS |  是  | String   | 128个字符，客户详细地址 |  
| CTAX_NUMBER_INFO |  是  | String   | 30个字符，客户纳税识别号 |  
| CTELEPHONE_INFO |  是  | String   | 20个字符，客户固定电话 |  
| CBANK_ACCOUNT_INFO |  是  | String   | 30个字符，客户银行账号 |  
| CBANK_NAME |  是  | String   | 256个字符，客户开户行名称 |  
| NETWORK_TYPE |  是  | String   | 1-水，2-电，3-气，4-热，5-冷，6-物业，7-房屋租赁 |  
| ACCOUNT_MONTH |  是  | Number   | 账务月份 |  
| TAX_EXCLUDE_AMOUNT |  是  | Number   | 不含税金额，精确到2位小数点 |  
  
说明：发票信息  
参数：ACC_INVOICE_DETAIL，类型：Array  
  

| 参数              | 必选 | 类型     | 描述             |  
| :----------------- | :----: | :-------- | :---------------- |  
| INVOICE_DID |  是  | String   | 16位字符，发票唯一的ID |  
| COMMODITY_CODE_INFO |  是  | String   | 20个字符，税收商品编码 |  
| GOODSNAME |  是  | String   | 64个字符，商品名称 |  
| AMOUNT |  是  | String   | 数量 |  
| PRICE |  是  | Number   | 单价，精确到4位小数点 |  
| TAX_INCLUDE_YESNO |  是  | String   | 1-不含税，2-含税 |  
| VAT_TAX_RATE |  是  | Number   | 增值税税率，精确到2位小数点 |  
| SPECIFICATION_INFO |  是  | String   | 20个字符，规格型号 |  
| UNIT_INFO |  是  | String   | 20个字符，单位 |  
| SELF_CODE_INFO |  是  | String   | 20个字符，自行编码 |  
| FAVOURED_POLICY_TYPE |  是  | String   | 优惠政策类型-待确认 |  
| ZERO_TAX_RATE_TYPE |  是  | String   | 1-免税，2-不征税，3-普通零税率 |  
| DEDUCTED_AMOUNT |  是  | Number   | 扣除额，精确到2位小数点 |  
| TAX_EXCLUDE_AMOUNT |  是  | Number   | 不含税金额，精确到4位小数点 |  
| TAX_AMOUNT |  是  | Number   | 税额，精确到2位小数点 |  
| TAX_INCLUDE_AMOUNT |  是  | Number   | 含税金额，精确到4位小数点 |  
  
说明：发票明细信息  
## 4、服务接口说明  
说明：无  
