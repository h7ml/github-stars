---
project: laravel-pay
stars: 1111
description: 可能是我用过的最优雅的 Alipay/WeChat/Unipay 的 laravel 支付扩展包了
url: https://github.com/yansongda/laravel-pay
---

Pay
===

依赖
--

-   php >= 8.0
-   composer
-   laravel || lumen >= 8.0

安装
--

composer require yansongda/laravel-pay:~3.7.0

### laravel 用户

#### 配置文件

php artisan vendor:publish --provider="Yansongda\\LaravelPay\\PayServiceProvider" --tag=laravel-pay

### lumen 用户

#### 配置文件

请手动复制配置文件

#### service provider

$app\->register(Yansongda\\LaravelPay\\PayServiceProvider::class);

使用方法
----

### 支付宝

use Yansongda\\LaravelPay\\Facades\\Pay;

$order = \[
    'out\_trade\_no' => time(),
    'total\_amount' => '1',
    'subject' => 'test subject - 测试',
\];

return Pay::alipay()->web($order);

// 下面这个方法也可以
// return Pay::web($order);

### 微信

use Yansongda\\LaravelPay\\Facades\\Pay;

$order = \[
    'out\_trade\_no' => time(),
    'body' => 'subject-测试',
    'total\_fee'      => '1',
    'openid' => 'onkVf1FjWS5SBIixxxxxxxxx',
\];

$result = Pay::wechat()->mp($order);

### 抖音支付

use Yansongda\\LaravelPay\\Facades\\Pay;

$order = \[
    'out\_order\_no' => date('YmdHis').mt\_rand(1000, 9999),
    'total\_amount' => 1,
    'subject' => '闫嵩达 - test - subject - 01',
    'body' => '闫嵩达 - test - body - 01',
    'valid\_time' => 600,
    'expand\_order\_info' => json\_encode(\[
        'original\_delivery\_fee' => 15,
        'actual\_delivery\_fee' => 10
    \])
\];

$result = Pay::douyin()->mini($order);

### 江苏银行(e融支付)

use Yansongda\\LaravelPay\\Facades\\Pay;

$order = \[
    'outTradeNo' => time().'',
    'proInfo' => 'subject-测试',
    'totalFee'\=> 1,
\];

$result = Pay::jsb()->scan($order);

具体使用说明请传送至 https://github.com/yansongda/pay

License
-------

MIT

Sponsor
-------
