参数 | 参数名称 | 类型 | 必填|描述 |范例
--------- | ------ | ----- | -------|---|-------------------
terminal_sn | 收钱吧终端ID |String(32)|Y|收钱吧终端ID，不超过32位的纯数字|"00101010029201012912"
client_auth_sn |商户系统预授权订单号  | String(32)|Y | 必须在商户系统内唯一；且长度不超过32字节|"18348290098298292838"
auth_sn| 收钱吧唯一预授权订单号|   String(16)|Y|收钱吧系统内部唯一预授权订单号|"7892259488292938"
total_amount | 订单金额 |String(10) |Y |以分为单位,不超过10位纯数字字符串,超过1亿元的收款请使用银行转账 |"1000"
operator |门店操作员  |String(32) |Y|发起本次交易的操作员 | Obama
subject |预授权支付订单标题  |String(32) |N|订单标题 | "千里香馄饨订单" ，不填默认商户名称 
auth_confirm_mode | 预授权完成模式 | String(12) |N | 不传默认NOT_COMPLETE ，可选COMPLETE 或 NOT_COMPLETE， COMPLETE:预授权完成后自动解冻剩余金额  NOT_COMPLETE:仅执行转支付给收款方
reflect  |反射参数  |String(64) |N|任何调用者希望原样返回的信息 | {"tips": "200"}
###返回参数说明
参数 | 参数名称 | 类型 | 必填|描述 |范例
--------- | ------ | ----- | -------|---|----
terminal_sn |终端号|   String(32)|Y|收钱吧终端ID|"01939202039923029"
auth_sn| 收钱吧唯一预授权订单号|   String(16)|Y|收钱吧系统内部唯一预授权订单号|"7892259488292938"
client_auth_sn|商户预授权订单号|    String(32)|Y|商户系统预授权订单号|"7654321132"
status|流水状态|String(32)| Y|本次操作产生的流水的状态| "SUCCESS"
order_status    |预授权订单状态   |String(32)|Y|当前预授权订单状态|"PAID"
payway| 支付方式|   String(2)|Y|一级支付方式，取值见附录《支付方式列表》|"1"
total_amount|订单金额 |String(10) |Y |订单金额 |"100"
finish_time |付款动作在收钱吧的完成时间|String(13)|Y|时间戳|"1449646835244"
channel\_finish_time|付款动作在支付服务商的完成时间|String(13)|Y|时间戳|"1449646835244"
operator    |操作员    |String(32) |Y  |门店操作员  |Obama
reflect |反射参数|  String(64)  |N| 透传参数    | {"tips": "200"}