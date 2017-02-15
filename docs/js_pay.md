# 发起JSSDK支付

## URL
   * 测试环境: http://qa.maxfun.co/qrcode?m=
   * 正式环境: https://tp.maxfun.co/qrcode?m=
   
## Request
```
{
    "tp_trade_no": "1000007", 
    "mch_key": "378284f3-31d4-4d75-8c3a-0c540ee6", 
    "total_fee": "1", 
    "nonce_str": "123213123"
}

对请求参数json串进行Base64加密，放到m=后面跳转url
例子:
对{"tp_trade_no":"1271TP1487057748363124","mch_key":"378284f3-31d4-4d75-8c3a-0c540ee67034","total_fee":1,"nonce_str":"zcmxk"}
进行Base64得到的加密串为:
eyJ0cF90cmFkZV9ubyI6IjEyNzFUUDE0ODcwNTc3NDgzNjMxMjQiLCJtY2hfa2V5IjoiMzc4Mjg0ZjMtMzFkNC00ZDc1LThjM2Et
MGM1NDBlZTY3MDM0IiwidG90YWxfZmVlIjoxLCJub25jZV9zdHIiOiJ6Y214ayJ9
把加密串放到m=后面,
即m=eyJ0cF90cmFkZV9ubyI6IjEyNzFUUDE0ODcwNTc3NDgzNjMxMjQiLCJtY2hfa2V5IjoiMzc4Mjg0ZjMtMzFkNC00ZDc1LThjM2Et
MGM1NDBlZTY3MDM0IiwidG90YWxfZmVlIjoxLCJub25jZV9zdHIiOiJ6Y214ayJ9
mVlIjowLjAxLCJub25jZV9zdHIiOiJ6Y214ayJ9
跳转url:
http://qa.maxfun.co/qrcode?m=ewogICAgInRwX3RyYWRlX25vIjogIjEwMDAwMDciLCAKICAgICJtY2hfa2V5IjogIjM3ODI4NGYzLTMxZDQtNGQ3NS04YzNhLTBjNTQwZWU2IiwgCiAgICAidG90YWxfZmVlIjogIjEiLCAKICAgICJub25jZV9zdHIiOiAiMTIzMjEzMTIzIgp9

```
参数说明：

<table data-tablesaw-sortable>
    <thead>
        <tr>
            <th data-tablesaw-sortable-col data-tablesaw-sortable-default-col>字段名称</th>
            <th data-tablesaw-sortable-col>类型</th>
            <th data-tablesaw-sortable-col>描述</th>
            <th data-tablesaw-sortable-col>是否必填</th>
        </tr>
		<tr>
            <td>mch_key</th>
            <td>字符型</th>
            <td>商户标识符</th>
            <td>是</th>
        </tr>
		<tr>
            <td>total_fee</th>
            <td>整型</th>
            <td>支付金额,单位:分</th>
            <td>是</th>
        </tr>
		<tr>
            <td>tp_trade_no</th>
            <td>字符型</th>
            <td>第三方交易订单号，回调时会回传这个订单号</th>
            <td>是</th>
        </tr>
		<tr>
            <td>nonce_str</th>
            <td>字符型</th>
            <td>随机字符串(建议每次请求都是随机生成的)</th>
            <td>是</th>
        </tr>
    </thead>
<table>

## JSSDK支付结果通知
* [JSSDK支付结果通知说明文档](https://github.com/maxfunapi/pay/blob/master/docs/async_notify.md)
