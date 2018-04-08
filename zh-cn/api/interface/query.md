# 预授权操作查询

## 接口名
{api_domain}/api/v1/pre-auth/query
## 请求类型
application/json
## 访问方式
POST
### 请求参数


| 参数 | 参数名称 | 类型 | 必填 | 描述 | 范例 |
| --- | --- | --- | --- | --- | --- |
| terminal\_sn | 收钱吧终端ID | String\(32\) | 特殊可选 | 收钱吧终端ID，不超过32位的纯数字 | "00101010029201012912" |
| request\_no | 收钱吧操作流水号 | String\(20\) | 特殊可选 | 收钱吧本次操作流水号 | "15154048770704543281" |
| client\_trans\_no | 商户系统操作请求流水号 | String\(36\) | 特殊可选 | 必须在商户系统内唯一；且长度不超过36字节 | "201802091001001" |

**request\_no与client\_trans\_no不能同时为空，优先按照request\_no查找，如果没有，再按照client\_auth\_sn查询**

### 返回参数说明

| 参数 | 参数名称 | 类型 | 必填 | 描述 | 范例 |
| --- | --- | --- | --- | --- | --- |
| terminal\_sn | 终端号 | String\(32\) | Y | 收钱吧终端ID | "01939202039923029" |
| auth\_sn | 收钱吧预授权唯一订单号 | String\(32\) | Y | 收钱吧系统内部唯一预授权订单号 | "7894259245320979"|
| client\_auth\_sn | 商户系统预授权订单号 | String\(32\) | Y | 必须在商户系统内唯一；且长度不超过32字节 | "1077735255938023" |
| request\_no | 收钱吧操作流水号 | String\(20\) | Y | 收钱吧本次操作流水号 | "15154048770704543281" |
| client\_trans\_no | 商户系统操作请求流水号 | String\(36\) | Y | 必须在商户系统内唯一；且长度不超过36字节 | "201802091001001" |
| status | 订单状态 | String\(32\) | Y | 当前订单状态 | "SUCCESS" |
| request\_type | 资金操作流类型 | String\(20\) | Y | 目前支持： FREEZE:冻结  UNFREEZE:解冻  PAY:支付 REFUND:退款 | "FREEZE" |
| amount | 该笔操作流水对应的金额 | String\(10\) | Y | 操作流水request\_no对应的金额 | "100" |
| payway | 支付方式 | String\(2\) | Y | 一级支付方式，取值见附录《支付方式列表》 | "1" |
| payer\_user\_id | 付款方ID | String\(64\) | Y | 支付平台对应唯一用户ID | "2088402019148643" |
| payer\_logon\_id | 付款方账号 | String\(128\) | Y | 支付平台对应付款方账号 | "134**3920" |
| subject | 预授权流水操作概述 | String\(32\) | Y | 流水操作概述 | "预授权订单" |
| request\_create\_time | 查询request\_no操作流水创建时间 | String\(13\) | Y | 时间戳 | "1449646835244" |
| request\_finish\_time | 查询request\_no操作流水完成时间 | String\(13\) | Y | 时间戳 | "1449646835244" |
| operator | 执行上次业务操作的操作员 | String\(32\) | Y | 操作员 | Obama |



