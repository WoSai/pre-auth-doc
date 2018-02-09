### 业务结果码列表

biz_response.data.status,状态分为：状态分为 SUCCESS、CLOSED、INIT和 UNKOWN 四类，

SUCCESS: 本次操作流水执行成功

CLOSED: 本次操作流水执行关闭

INIT: 本次操作流水进行中

UNKOWN: 本次业务执行结果未知

具体到业务场景，分别有下列状态：

取值 |含义 | 下一步动作 
--------- | ------ | -----  
<font color="red">INVOICE_SUCCESS</font>|	开票操作成功	| 
<font color="red">INVOICE_FAIL</font>	| 开票操作失败	| 
<font color="red">INVOICE_IN_PROGRESS</font> | 开票中  | 用户方接口接受开票结果的主动推送，或者发起被动查询查看开票结果
<font color="red">SUCCESS|	操作成功,**开发者根据返回的biz_response.data.task_status属性判断当前开票任务的状态。**| 
<font color="red">FAIL	|操作失败（不会触发流程）| 
<font color="red">INVOICE_NOT_EXIST	|没有查到相关票据或开票信息| 

### 任务状态列表

biz_response.data.task_status	

取值 |含义  
--------- | ------
<font color="green">CREATED</font>	| <font color="red">任务已创建/开票中</font>

**开发者根据返回的biz_response.data.task_status属性判断当前开票任务的状态。**

### 哪些状态是任务最终状态
- 开票任务查询接口(query) 返回的 SUCCESS  


### 流水状态列表

取值 |含义 | 处理逻辑 
--------- | ------ | -----  
SUCCESS	|业务执行确认成功|



### 业务执行错误码列表

biz_response.error_code为业务执行结果返回码；biz_response.error_message为对应的中文描述,

当业务执行失败(即biz_response.result不为success)的时候，会返回如下内容

error_code |error_message
--------- | ------
TASK_TIMEOUT | 任务超时

 * 备注：当系统返回状态是失败时，但不能确认用户客户端的状态时，可以人工介入，联系客服人员，以防遭受损失。