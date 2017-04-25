# AdPlatformProtocol
协议说明
通用请求协议说明

## 请求模板
> http://domain/产品类型/接口名称?s=参数加密

## 例子：

### 插屏请求
>http://domain/spot/req?i={appid}&s=xxxxxxxxxxxxxxxxxxxx  

### 插屏效果记录
>http://domain/spot/eff?i=xxxxxxxxxxxx&s=xxxxxxxxxxxxxxxxxxxx&rsd=rsd&e=e&pdt=1;

## 参数模板

| 参数        | 类型           | 说明  |
| ------------- |:-------------:| -----:|
| i      | string | appid |
| s      | string | s参数 |
| rsd      | string | rsd参数，效果记录用到，通过请求返回 |
| e      | string | e参数，效果记录用到，通过请求返回 |
| pdt      | int | 效果步骤,效果记录用到 |


## PDT步骤标识

| 步骤名称        | 字段           |
| ------------- |:-------------:|
|   展示    | 0 |
|   点击    | 1 |
|   下载成功    | 2 |
|   安装成功    | 3 |
|   开始下载    | 6 |
|   开始安装    | 7 |


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

s参数sjon例子：
<pre><code>
 {
    "smv":"1",
    "ext":{}
    "ei": "863598020431614",
    "si": "460000360914810",
    "bd": "",
    "andid": "",
    "cid": "Gv6jkqsfVMsJ",
    "dd": "umi3(td)",
    "mac": "00082200c124",
    "dv": "alps",
    "po": "kltezm-user 4.4.2 KOT49H G9008VZMU1ANCH release-keys",
    "sw": "720",
    "sh": "1280",
    "sd": "",
    "fei": "863598020431614",
    "fsi": "460025168530410",
    "gvid": "",
    "scid": "",
    "sds": "1",
    "osv": "android 4.2.2",
    "attr": 0,
    "tid": "",
    "apn": "wifi",
    "cn": "TW Mobile",
    "lat": "",
    "lon": "",
    "bsi": "0|466|97|21004867|31113",
    "cc": "CN",
    "lc": "zh",
    "nt": "4",
    "bssid": "8c0000190012",
    "rb": "0",
    "usb": "0",
    "rt": 1422265610
    "avn": "1.0.1",
    "pn": "com.syezon.wifi",
    "user": "o0GHhsm6xi8JeZG-rLAcvMO8plbQ",
    "chn": "0"
    "sv": "5.0.0",
    "spc": "10050",
    "pd": 0,
    "ts": 0,
    "ise": 0,
    "rot": 0,
    "3gst":1232145,
    "hv":1,
    "upid":"b9a316ab400d7a55"
    "pkpid":"84706e5ff6be82c9caaecc2f2edaae82"
    "sn":"01abc07fdad7add8"
}
</code></pre>


插屏返回结果：

## 返回参数说明：

| 参数        | 类型           | 说明  |
| ------------- |:-------------:| -----:|
| c      | int | 错误码 0为成功 |
| ad      | string | 广告列表，以json数组形式表达 |

## ad参数说明

| 参数        | 类型           | 说明  |
| ------------- |:-------------:| -----:|
| spotid      | int | 插屏广告ID |
| md5      | string | 广告MD5码,通过广告链接生成 |
| rsd      | string | 	随机字符串（10位） |
| e      | string | e参数，广告生成的唯一字符串，与rsd一起用于后面的统计接口中 |
| name      | string | 应用名/广告名 |
| pn      | string | 应用包名 |
| siu      | string | 应用图标，选填 |
| app      | string | APK广告下载地址，和url只需要填其中一个 |
| tips      | string | 广告提示语 |
| url      | string | 网页广告跳转地址，和app只需要填其中一个 |
| rtg      | string | 广告方图json，目前方图和竖图一样，格式参照例子 |
| blk      | string | 广告竖图，目前方图和竖图一样，格式参照例子 |


<pre><code>
{
	"c": 0,
	"ad": [{
		"spotid": 5,
		"md5": "1786cb09b8fc244f216fa63314f4b208",
		"rsd": "3332433344",
		"e": "6-kTLf11nip9KWYIyW4gvuVgy9txb9gbydHxLqQ-O1C1fiMtyJ7Nbagd2tpFchIpars62P6Jf03zDo1oCmXRa9dumJ6yb1kWThLiWeQWy6Fif_3Lzw9sCEeQ_aaRuNjVyKICaxwFOJHiGp_tiyXUeWSA95tTLaA9y5HBe_MYy1S2v__p2F4Oq_hci1cRfte9PdniWCPIyiWmv61JiCXNfV3tDVbxGWvdD5nhLBA-3BQ",
		"name": "[\u6d4b\u8bd5]\u53e3\u888b\u4e66\u5c4b",
		"pn": "com.duobao.android",
		"siu": "http:\/\/creative-img.ymcdn.cn\/1604\/f6\/c6\/8378c4adf36849f6.jpg",
		"app": "http:\/\/pkg-cdn-app.ymcdn.cn\/1508\/d3\/a220f68f02672a10.apk",
		"tips": "\u6d77\u91cf\u85cf\u4e66\uff0c\u6587\u5b66\u76db\u5bb4\uff01",
		"url": "",
		"rtg": {
			"pic": "http:\/\/img-cdn-spot.ymcdn.cn\/res\/5\/14606938880.jpg",
			"uri": ""
		},
		"blk": {
			"pic": "http:\/\/img-cdn-spot.ymcdn.cn\/res\/2016\/04\/5-e6768378c4.jpg",
			"uri": ""
		}
	}]
}
</code></pre>
