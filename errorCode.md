# 错误码

## 规格说明

业务级异常，使用 1-001-001-001 段

一共 10 位，分成三段

- 第一段，1 位，类型。
    - 1 - 业务级别异常
	- 2 - 系统级别异常

- 第二段，3 位，系统类型。
	- 001 - 用户系统
	- 002 - 商品系统
	- 003 - 订单系统
	- 004 - 支付系统
	- 005 - 优惠劵系统

- 第三段，3 位，模块。
一般建议，每个系统里面，可能有多个模块，可以再去做分段。
	- 001 - OAuth2 模块
	- 002 - User 模块
	- 003 - MobileCode 模块

- 第四段，3 位，错误码。
一般建议，每个模块自增。
	- 001 - 订单支付失败

## 错误码解析

|--|--|--|--|
|module|property|code|message|
|**系统权限**|
|OAUTH2模块|OAUTH2_INVALID_GRANT_BAD_CREDENTIALS|1001001|密码不正确|
|**会员系统**|
|用户模块|USER_MOBILE_NOT_REGISTERED|1002001|手机号未注册用户|
|**订单订单**|
|订单模块|ORDER_NOT_EXISTENT|1003001|获取订单不存在|
|**购物车系统**|
|订单模块|ORDER_NOT_EXISTENT|1003001|获取订单不存在|
|**支付系统**|
|支付模块|PAY_REFUND_ERROR|1007001|退款失败|
|**商品系统**|
|商品模块|GOODS_NOT_EXISTENT|1008001|获取商品不存在|
|**促销系统**|
|**财务管理系统**|
|**客服系统**|
|**风控系统**|
|**物流系统**|
|**库存系统**|