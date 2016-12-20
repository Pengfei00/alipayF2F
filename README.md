# AlipayF2F-python
支付宝当面付python API.

#快速上手
1.pip install rsa

2.引入alipay文件到项目

3.创建alipay实例需传入app_id,private_key,public_key,还有可选的notify_url异步回调地址等


__预创建订单__

创建一个alipay实例

`alipay = alipay(APPID,private_key,public_key,notify_url)`

然后使用trade_pre_create就能生产一个二维码了

`alipay.trade_pre_create("商户订单号","订单总金额","订单标题",)`

正常状态下会返回一个二维码的地址，生成二维码给用户扫就可以了

__用户扫码支付__

用户扫码后支付宝会访问创建实例时提供的`notify_url`

如果想确定是否是支付宝访问只需要使用`parse_response`解析支付宝post来的数据即可

如果为支付宝传回记得返回`success`来告诉支付宝已收到


__退款__

使用`trade_refund`方法退款

