# JSSDK支付结果通知

	交易成功时，往第三方告知的url发送支付结果通知.

## URL
   通知url，在创建商户时配置

## Method
   POST

## Headers
```
   Content-type=application/json
```

## Request
```
{
    "identifier": "o9dNzw96W2W6ni3f3ZdQ2_EGsBPM",
    "mch_key": "378284f3-31d4-4d75-8c3a-0c540ee67034",
    "tp_trade_no": "1484657785743165",
    "pay_status": 1,
    "payment_type": 1,
    "total_fee": 1,
    "out_trade_no": "1271TP1487057748363124",
    "sign":"e0f2c29f7042d156cc5bac9758acb2d1"
}

sign签名生成方式:
通过传递的参数按首字母排序拼接(值为空的去掉)，最后拼上mch_key生成一个字符串，对此字符串进行MD5加密得到sign值
例子：
对此字符串进行MD5加密
identifier=o9dNzw96W2W6ni3f3ZdQ2_EGsBPM&out_trade_no=1271TP1487057748363124&pay_status=1&payment_type=1&total_fee=1&tp_trade_no=1484657785743165&mch_key=378284f3-31d4-4d75-8c3a-0c540ee67034
得到，e0f2c29f7042d156cc5bac9758acb2d1，sign不区分大小写

```
<table data-tablesaw-sortable>
    <thead>
        <tr>
            <th data-tablesaw-sortable-col data-tablesaw-sortable-default-col>字段名称</th>
            <th data-tablesaw-sortable-col>类型</th>
            <th data-tablesaw-sortable-col>描述</th>
        </tr>
		<tr>
			<td>pay_status</th>
			<td>数字</th>
			<td>付款状态: 0-未付款 1-已支付 3-取消支付订单 4-已退款</th>
		</tr>
		<tr>
			<td>identifier</th>
			<td>字符串</th>
			<td>用户标识符, pay_status等于1才有返回</th>
		</tr>
		<tr>
			<td>mch_key</th>
			<td>字符串</th>
			<td>商户标识符</th>
		</tr>
		<tr>
            <td>total_fee</th>
            <td>整型</th>
            <td>支付金额,单位:分</th>
            <td>是</th>
        </tr>
		<tr>
			<td>payment_type</td>
			<td>数字</td>
			<td>支付方式: 1-微信 2-支付宝 4-京东支付 5-QQ支付</td>
		</tr>
		<tr>
			<td>tp_trade_no</td>
			<td>字符串</td>
			<td>商户订单号</td>
		</tr>
		<tr>
			<td>out_trade_no</td>
			<td>字符串</td>
			<td>交易单号</td>
		</tr>
    </thead>
<table>
