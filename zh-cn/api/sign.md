# 签名机制

## 请求域名
   
   <font color="red">**注：收钱吧的Web API接口是https协议，当发起请求时，会要求检查证书，在发起请求时规避ssl的证书检查或者
  携带证书请求**</font>
    
## 需要参与签名的接口及参数

需要使用服务商序列号(vendor_sn)和服务商密钥(vendor_key)进行签名的接口：
   
   * 1.激活接口(/terminal/activate)
     
需要使用激活得到的终端号(terminal_sn)和终端密钥(terminal_key)进行签名的接口:
   
   * 1.签到
   * 2.预授权
   * 3.预授权撤销
   * 4.预授权操作查询
   * 5.预授权完成
   * 6.预授权完成退款
   * 7.预授权流程操作记录查询
   
    <font color="red">**注：如果使用了签到接口，请以签到返回的terminal_sn和terminal_key作为其他接口的签名参数**</font>

     
## 签名方法
   如果要正常使用各接口，需要按照以下方式去进行签名验证:
   
   * 本平台所有的API仅支持JSON格式的请求调用，请务必在HTTP请求头中加入`Content-Type: application/json`。
   * 所有请求的body都需采用`UTF-8`编码，所有响应也会采用相同编码。
   * 支付平台所有的API调用都需要签名验证。
   * 采用应用层签名机制。将HTTP请求body部分的`UTF-8`编码字节流视为被签名的内容，不关心主体的格式。
   * 签名人序列号(sn)和签名值(sign)放在HTTP请求头中，在接入服务中统一校验。
   * 签名算法: sign = MD5( CONCAT( body + key ) )
   * 签名首部: `Authorization: sn + " " + sign`
   * 所有返回参数都为 <font color="red">**JSON**</font> 格式，请务必在HTTP请求头中加入Content-Type: application/json。
   * 所有请求的body都需采用UTF-8编码，所有响应也会采用相同编码。
   * 所有返回数据的类型都是 <font color="red">**字符串**</font>。
   * 接口中所有涉及金额的地方都以 <font color="red">**分**</font> 为单位。
   * 所有接口, 无论是收钱吧提供,或是需要用户自己实现的接口 ,http请求都需要使用 `UTF-8` 编码
   


