## 1、接口描述  
服务接口：(QueryLadderPopulation)查询阶梯人口增减量配置  
接口描述：查询阶梯人口增减量配置  
请求说明：POST https://api.epeis.com/Service/v1/QueryLadderPopulation/  
  
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
	"SYS_PAGE":	{
		"PAGE_NO":	1,
		"PAGE_ROWS":	8
	},
	"COM_LAD_POPUL":	{
		"RETAIL_CO_DID":	"",
		"RET_STORES_AID":	"",
		"ADMIN_CODE_INFO":	""
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
  
参数：SYS_PAGE，类型：object  
  
| 参数 | 必选 | 类型 | 长度 | 精度 | 描述 |  
| :----------------- | :----: | :-------- | :----: | :----: | :---------------- |  
| PAGE_NO       |  是  | Number   | 4 | 0 | 第几页，必须大于“0” |  
| PAGE_ROWS     |  是  | Number   | 4 | 0 | 每页行数，必须大于“0” |  
  
参数：COM_LAD_POPUL，类型：object  
  
| 参数              | 必选 | 类型     | 长度 | 精度 | 描述             |  
| :----------------- | :----: | :-------- | :----: | :----: | :---------------- |  
| RETAIL_CO_DID |  否  | String   | 16 | 0 | 16个字符，销售公司编码 |  
| RET_STORES_AID |  否  | String   | 16 | 0 | 16个字符，销售公司营业网点ID |  
| ADMIN_CODE_INFO |  否  | String   | 20 | 0 | 20个字符，行政区划 |  
  
说明：阶梯人口增减量配置  
  
## 3、服务接口响应参数  
#### 3.1、响应参数报文示例  
~~~  
{
	"CODE":	0,
	"MESSAGE":	"",
	"DATA":	{
		"SYS_PAGE":	{
			"PAGE_NO":	1,
			"PAGE_ROWS":	8,
			"NEXT_YESNO":	"2",
			"TOTAL":	1000
		},
		"COM_LAD_POPUL":	{
			"RETAIL_CO_DID":	"",
			"RET_STORES_AID":	"",
			"ADMIN_CODE_INFO":	"",
			"NETWORK_TYPE":	"",
			"POPULATION_BASE":	0,
			"POPULATION_INCREMENT":	0,
			"INCREASE_REDUCE":	0
		}
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
  
参数：SYS_PAGE，类型：object  
  
| 参数              | 必选 | 类型     | 描述             |  
| :----------------- | :----: | :-------- | :---------------- |  
| PAGE_NO       |  是  | Number   | 第几页 |  
| PAGE_ROWS     |  是  | Number   | 每页行数 |  
| NEXT_YESNO    |  是  | String   | 是否有下页，1-无，2-有 |  
| TOTAL         |  是  | Number   | 总行数 |  
  
参数：COM_LAD_POPUL，类型：object  
  

| 参数              | 必选 | 类型     | 描述             |  
| :----------------- | :----: | :-------- | :---------------- |  
| RETAIL_CO_DID |  否  | String   | 16个字符，销售公司编码 |  
| RET_STORES_AID |  否  | String   | 16个字符，销售公司营业网点ID |  
| ADMIN_CODE_INFO |  否  | String   | 20个字符，行政区划 |  
| NETWORK_TYPE |  否  | String   | 1-水，2-电，3-气，5-冷 |  
| POPULATION_BASE |  否  | Number   | 人口基数 |  
| POPULATION_INCREMENT |  否  | Number   | 人口增量 |  
| INCREASE_REDUCE |  否  | Number   | 增减量 |  
  
说明：阶梯人口增减量配置  
## 4、服务接口说明  
说明：无  
