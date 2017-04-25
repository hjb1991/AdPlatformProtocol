# AdPlatformProtocol
协议说明
通用请求协议说明

## 请求模板
> http://domain/产品类型/接口名称?s=参数加密

## 例子：

### 插屏请求
>http://domain/spot/req?i={appid}&s=xxxxxxxxxxxxxxxxxxxx  

### 插屏展示记录  
>http://domain/spot/show?i=xxxxxxxxxxxx&s=xxxxxxxxxxxxxxxxxxxx

## s参数说明：

s参数为用户参数表
以json形式通过AES加密形成字符串

秘钥：dnQkZGRnbDFwYmI3N3heaA==  
秘钥通过base64编码形成


| 参数        | 类型           | 说明  |
| ------------- |:-------------:| -----:|
| ext      | string | 扩展参数，暂不用 |
| andid      | string | AndroidID |
| smv      | string | 协议版本号 |
| bd      | string | 蓝牙地址 |
| cid      | string | 用户ID，通过IMEI等参数生成 |
| dd      | string | 设备机型 |
| dv      | string | 设备制造商 |
| imei      | string | IMEI |
| imsi      | string | IMSI |
| mac      | string | 设备MAC地址 |
| sd      | int | 屏幕密度 |
| sw      | int | 屏幕宽度 |
| sh      | int | 屏幕宽度 |
| sds      | int | SD卡是否可用 |
| ise      | int | 是否模拟器 |
| rot      | int | 是否root过 |
| apn      | string | 当前接入apn名称 |
| cn      | string | 运营商 |
| cc      | string | 国家编码 |
| nt      | string | 网络类型 |
| bssid      | string | WiFi ID |
| hv      | string | 屏幕状态 1：竖屏 2：横屏 |
| pn      | string | 应用包名 |
| avn      | string | 应用版本号 |
| osv      | int | 系统版本号,如17，18.19 |
| rt      | long | 当前时间戳 |
| sv      | int | sdk版本号 |





插屏返回结果：
