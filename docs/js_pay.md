# 发起JSSDK支付

## URL
   测试环境: http://qa.maxfun.co/qrcode?m=
   正式环境:
   
## Request
```
{
    "tp_trade_no": "1271TP1487057748363124",
    "mch_key": "hkdrg",
    "total_fee": 0.01,
	"nonce_str":"zcmxk"
}

对请求参数进行Base64加密，放到m=后面跳转页面
例子:
Base64('{"tp_trade_no":"1271TP1487057748363124","mch_key":"hkdrg","total_fee":0.01,"nonce_str":"zcmxk"}');
String str = "eyJ0cF90cmFkZV9ubyI6IjEyNzFUUDE0ODcwNTc3NDgzNjMxMjQiLG1jaF9rZXk6ImhrZHJnIiwidG90YWxfZmVlIjowLjAxfQ==";

跳转url=http://qa.maxfun.co/qrcode?m=eyJ0cF90cmFkZV9ubyI6IjEyNzFUUDE0ODcwNTc3NDgzNjMxMjQiLCJtY2hfa2V5IjoiaGtkcmciLCJ0b3RhbF9mZWUiOjAuMDEsIm5vbmNlX3N0ciI6InpjbXhrIn0=

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
            <td>tp_trade_no</th>
            <td>字符型</th>
            <td>商户订单号</th>
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