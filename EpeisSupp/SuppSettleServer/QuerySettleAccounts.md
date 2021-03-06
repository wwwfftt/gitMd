## 1、接口描述  
服务接口：(QuerySettleAccounts)查询结算户账户  
接口描述：查询结算户账户  
请求说明：POST https://api.epeis.com/Service/v1/QuerySettleAccounts/  
  
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
	"INOUT_SETTLE_ACCOUNT":	{
		"CERTIFICATES_INFO":	"",
		"MOBILE_PHONE_INFO":	"",
		"ACC_CERT_INFO":	"",
		"CUSTOMER_NAME":	"",
		"ADDRESS":	"",
		"NETWORK_TYPE":	""
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
  
参数：INOUT_SETTLE_ACCOUNT，类型：object  
  
| 参数              | 必选 | 类型     | 长度 | 精度 | 描述             |  
| :----------------- | :----: | :-------- | :----: | :----: | :---------------- |  
| CERTIFICATES_INFO |  否  | String   | 20 | 0 | 证件号码 |  
| MOBILE_PHONE_INFO |  否  | String   | 20 | 0 | 手机号码 |  
| ACC_CERT_INFO |  否  | String   | 20 | 0 | 账户证件号码 |  
| CUSTOMER_NAME |  否  | String   | 256 | 0 | 客户名称 |  
| ADDRESS |  否  | String   | 128 | 0 | 详细地址 |  
| NETWORK_TYPE |  否  | String   | 2 | 0 | 管网类型：1-水；2-电；3-气；4-热；5-冷；6-物业；7-房屋租赁 |  
  
说明：结算信息  
  
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
		"SETTLE_ACCOUNT":	[{
				"CUSTOMER_DID":	"",
				"CUSTOMER_DID_MC":	"",
				"USER_CUS_DID":	"",
				"USER_CUS_DID_MC":	"",
				"USER_ACCOUNT_AID":	"",
				"SETTLEMENT_AID":	"",
				"SETTLEMENT_NAME":	"",
				"NETWORK_TYPE":	"",
				"ADDRESS":	"",
				"OWE_BALANCE":	0,
				"ATTESTATION_TYPE":	"",
				"CONTROL_TYPE":	"",
				"SALE_CO_DIMENSION":	"",
				"INDUSTRY_CODE_INFO":	"",
				"INDUSTRY_TYPE":	"",
				"NETWORK_CO_DIMENSION":	"",
				"RESIDENT_YESNO":	"",
				"CITY_YESNO":	"",
				"ARMY_YESNO":	"",
				"TEMPORARY_YESNO":	"",
				"PUBLIC_USE_YESNO":	"",
				"CONNECT_MODE_TYPE":	"",
				"TALLY_CYCLE":	0,
				"LAST_CHECK_DATE":	0,
				"BUSI_PROC_DID":	"",
				"BUS_CATEG_TYPE":	"",
				"REMARK_INS":	"",
				"SIGN_CONTRACT_YESNO":	"",
				"CONTRACT_NUM":	"",
				"CON_DEADLINE_DATE":	0
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
  
参数：SYS_PAGE，类型：object  
  
| 参数              | 必选 | 类型     | 描述             |  
| :----------------- | :----: | :-------- | :---------------- |  
| PAGE_NO       |  是  | Number   | 第几页 |  
| PAGE_ROWS     |  是  | Number   | 每页行数 |  
| NEXT_YESNO    |  是  | String   | 是否有下页，1-无，2-有 |  
| TOTAL         |  是  | Number   | 总行数 |  
  
参数：SETTLE_ACCOUNT，类型：Array  
  

| 参数              | 必选 | 类型     | 描述             |  
| :----------------- | :----: | :-------- | :---------------- |  
| CUSTOMER_DID |  是  | String   | 客户账户ID |  
| CUSTOMER_DID_MC |  是  | String   | 客户账户名称 |  
| USER_CUS_DID |  是  | String   | 使用者客户ID |  
| USER_CUS_DID_MC |  是  | String   | 使用者客户名称 |  
| USER_ACCOUNT_AID |  是  | String   | 用户账户ID |  
| SETTLEMENT_AID |  是  | String   | 结算账户ID |  
| SETTLEMENT_NAME |  是  | String   | 结算户姓名 |  
| NETWORK_TYPE |  是  | String   | 管网类型：1-水；2-电；3-气；4-热；5-冷；6-物业；7-房屋租赁 |  
| ADDRESS |  是  | String   | 结算信息地址 |  
| OWE_BALANCE |  是  | Number   | 欠费 |  
| ATTESTATION_TYPE |  是  | String   | 用户认证类型：1-未认证；2-审核中；3-已认证 |  
| CONTROL_TYPE |  是  | String   | 量控费控类型：1-量控；2-费控 |  
| SALE_CO_DIMENSION |  是  | String   | 销售公司统计维度 |  
| INDUSTRY_CODE_INFO |  是  | String   | 行业分类 |  
| INDUSTRY_TYPE |  是  | String   | 产业分类：1-第一产业；2-第二产业；3-第三产业 |  
| NETWORK_CO_DIMENSION |  是  | String   | 管网公司统计维度 |  
| RESIDENT_YESNO |  是  | String   | 是否居民：1-否；2-是 |  
| CITY_YESNO |  是  | String   | 是否城市：1-否；2-是 |  
| ARMY_YESNO |  是  | String   | 是否军工：1-否；2-是 |  
| TEMPORARY_YESNO |  是  | String   | 是否临时：1-否；2-是 |  
| PUBLIC_USE_YESNO |  是  | String   | 是否公用：1-否；2-是 |  
| CONNECT_MODE_TYPE |  是  | String   | 接线类型：1-A相；2-B相；3-C相；4-三相三线；5-三相四线 |  
| TALLY_CYCLE |  是  | Number   | 点检周期 |  
| LAST_CHECK_DATE |  是  | Number   | 上次检查日期 |  
| BUSI_PROC_DID |  是  | String   | 业务办理编码 |  
| BUS_CATEG_TYPE |  是  | String   | 业务类别：1-新装；2-变更不结费；10-过户；11-变更结费；12-销户；13-特殊追补 |  
| REMARK_INS |  是  | String   | 备注说明 |  
| SIGN_CONTRACT_YESNO |  是  | String   | 是否签订合同：1-否；2-是 |  
| CONTRACT_NUM |  是  | String   | 合同编号 |  
| CON_DEADLINE_DATE |  是  | Number   | 合同期限 |  
  
说明：结算信息  
## 4、服务接口说明  
说明：无  
