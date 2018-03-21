# 接口响应

### 返回字段列表

字段名 | 字段含义 | 取值 | 备注
--------- | ------ | ----- | -------
result_code | 通讯响应码 |200，400，500|200：通讯成功；400：客户端错误；500:服务端错误
error_code  | 通讯错误码 |见附录《公共错误码》 |通讯 **失败** 的时候才返回
error_message  |通讯错误信息描述 |见附录《公共错误码》 |通讯 **失败** 的时候才返回
biz_response  | 业务响应数据 |数组结构 |通讯 **成功** 的时候才返回
biz\_response.result_code  | 业务执行结果码 |见附录《业务结果码》|
biz\_response.error_code  | 业务执行结果返回码 | |
biz\_response.error_message  |业务执行错误信息 | |
biz\_response.data.auth_sn  | 收钱吧预授权订单号 | 字符串 |业务执行 **成功** 才返回
biz\_response.data.request_no  | 收钱吧操作流水号 | 字符串 |业务执行 **成功** 才返回
biz\_response.data.client_auth_sn  | 商户系统预授权订单号 | 字符串 |业务执行 **成功** 才返回
biz\_response.data.client_trans_no  | 商户操作请求流水号 | 字符串 |业务执行 **成功** 才返回
biz\_response.data.amount  | 本次流水操作金额 |整数，以 <font color="red">分</font> 为单位 |
biz\_response.data.payway  | 预授权支付的支付方式 | 2:支付宝 | 业务执行 **成功**才返回
biz\_response.data.terminal_sn  | 发起本次业务请求的终端ID |字符串| 业务执行 **成功**才返回
biz_response.data.data.subject | 本次预授权操作概述 |字符串 |业务执行 **成功**才返回
biz_response.data.request_type  | 本次资金操作类型 |05：冻结 16:解冻 07:支付 18:退款 |业务执行类型
biz_response.data.operator  | 本次业务执行的操作员 |字符串 |业务执行 **成功**才返回
biz_response.data.payer_user_id | 付款方ID |字符串 |支付平台对应唯一用户ID
biz_response.data.payer_logon_id | 付款方账号 |字符串 |支付平台对应付款方账号
biz_response.data.reflect | 商户透传参数 |字符串 |业务执行 **成功**才返回

