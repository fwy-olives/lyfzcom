﻿
## 安装

* 通过composer，这是推荐的方式，可以使用composer.json 声明依赖，或者运行下面的命令。SDK 包已经放到这里 [`fwy-olives/lyfzcom`][install-packagist] 。
```bash
$ composer require fwy-olives/lyfzcom
```
* 直接下载安装，SDK 没有依赖其他第三方库，但需要参照 composer的autoloader，增加一个自己的autoloader程序。

## 运行环境

|  SDK版本 | PHP 版本 |
|:--------------------:|:---------------------------:|
|          1.X         |  cURL extension,   5.6,7.0 |


## 使用方法
/--企业中心 start--/
### 获取toke
```php
use Lyfzcom\Emc;
...
生 产 环 境
    $auth = new Emc($accessKey, $secretKey);
    $token = $auth->getAccessToken();
...
测试 环境
    $Lyfzcom = new Lyfzcom();
    $auth = new Emc($accessKey, $secretKey,"dev");
    $token = $auth->getAccessToken();
...
tp
$auth = new \Lyfzcom\Emc($accessKey, $secretKey);
$token = $auth->getAccessToken();
```
主动获取或推送
$auth->setAccessToken($token);
$ret=$auth->companyList($uid);

/--企业中心 end--/
/--登录中心 start--/
登录中心
### 获取toke
```php
use Lyfzcom\Sso;
...
生产环境
    $auth = new Sso($accessKey, $secretKey);
    $token = $auth->getAccessToken();
...
测试环境
    $Lyfzcom = new Lyfzcom();
    $auth = new Sso($accessKey, $secretKey,"dev");
    $token = $auth->getAccessToken();
...
tp
$auth = new \Lyfzcom\Sso($accessKey, $secretKey);
$token = $auth->getAccessToken();
```
主动推送或推送
$auth->setAccessToken($token);
$ret=$auth->addUser($data);
/--登录中心 end--/
