# 刷卡支付

	提交刷卡支付请求数据

## URL
   {BASE_URL}/maxfunpay/services/tp/scan_pay

## Method
   POST

## Headers
```
   Content-type=application/json
```

## Request
```
{
	"mch_key":"111333",
	"auth_code":"130149729103798799",
	"total_fee":0.01,
	"nonce_str":"azfkglz",
	"sign":"13003131421f050fbcbf54939897c0f0"
}

sign签名生成方式:
auth_code=&nonce_str=&total_fee&mch_key=
通过传递的参数按首字母排序拼接，最后拼上mch_key生成一个字符串，对此字符串进行MD5加密得到
例子：
对此字符串进行MD5加密
auth_code=130149729103798799&nonce_str=azfkglz&total_fee=0.01&mch_key=111333
得到，13003131421f050fbcbf54939897c0f0，sign不区分大小写

```
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
            <td>auth_code</th>
            <td>字符型</th>
            <td>用户付款码</th>
            <td>是</th>
        </tr>
		<tr>
            <td>total_fee</th>
            <td>数字(Double)</th>
            <td>支付金额,单位:元</th>
            <td>是</th>
        </tr>
		<tr>
            <td>nonce_str</th>
            <td>字符型</th>
            <td>随机字符串</th>
            <td>是</th>
        </tr>
        <tr>
            <td>sign</th>
            <td>字符型</th>
            <td>数据签名</th>
            <td>是</th>
        </tr>
    </thead>
<table>


## Response
```
{
  "status": {
    "code": "200",
    "message": "success"
  },
  "result": {
    "ret": 0,
    "msg": "支付成功",
    "identifier": "o9dNzw96W2W6ni3f3ZdQ2_EGsBPM",
    "totalFee": 0.01,
    "payment_type": 1,
	"out_trade_no":"1271TP1486985534418791"
  }
}
```
<table data-tablesaw-sortable>
    <thead>
        <tr>
            <th data-tablesaw-sortable-col data-tablesaw-sortable-default-col>字段名称</th>
            <th data-tablesaw-sortable-col>类型</th>
            <th data-tablesaw-sortable-col>描述</th>
        </tr>
		<tr>
			<td>ret</th>
			<td>数字</th>
			<td>为0即支付成功，其他值即交易失败</th>
		</tr>
		<tr>
			<td>msg</th>
			<td>字符串</th>
			<td>返回信息，例如错误信息</th>
		</tr>
		<tr>
			<td>identifier</th>
			<td>字符串</th>
			<td>用户标识符, ret等于0才有返回</th>
		</tr>
		<tr>
		<tr>
			<td>totalFee</th>
			<td>数字(Double)</th>
			<td>交易金额</th>
		</tr>
		<tr>
			<td>payment_type</td>
			<td>数字</td>
			<td>1微信 2支付宝 4京东支付 5QQ支付</td>
		</tr>
		<tr>
			<td>out_trade_no</td>
			<td>字符串</td>
			<td>交易单号</td>
		</tr>
    </thead>
<table>
