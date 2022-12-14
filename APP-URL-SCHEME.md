### URL Scheme 数据清洗命令

```
cat AndroidManifest.xml|perl -ne 'print if /<data android:host=/'|
perl -pe 's/^.*<data android:host="(.*?)" android:path="(.*?)" android:scheme="(.*?)"\/>/\3:\/\/\1\2/'|
perl -pe 's/^.*<data android:host="(.*?)" android:scheme="(.*?)"\/>/\2:\/\/\1/'|
perl -pe 's/^.*<data android:host="(.*?)" android:pathPrefix="(.*?)" android:scheme="(.*)"\/>/\3:\/\/\1\2/'|
perl -pe 's/^.*<data android:host="(.*?)" android:pathPattern="(.*?)" android:scheme="(.*)"\/>/\3:\/\/\1\2/' > ' URL Scheme.txt'
```

### 淘宝

相机拍照搜索

```
taobao://tb.cn/n/scancode
```

搜索指定物品

```
taobao://s.taobao.com?q=[prompt:商品名称]
```

使用天猫搜索

```
taobao://list.tmall.com/search_product.htm?q=[prompt:商品名称]
```

取件身份码

```
taobao://m.taobao.com/tbopen/index.html?h5Url=https://market.m.taobao.com/app/cn-yz/multi-activity/authCode.html
```

搜索指定店铺

```
taobao://shopsearch.taobao.com/search?app=shopsearch&q=[prompt:店铺名称]
```

跳转指定淘宝店铺

```
taobao://shop.m.taobao.com/shop/shop_index.htm?shopId=[prompt:店铺 ID]
```

### 天猫

```
tmall://page.tm/search?q=[prompt:商品名称]
```

### 美团外卖

```
meituanwaimai://waimai.meituan.com/search?query=[prompt:商品名称]
```

### 豆瓣

搜索内容

```
douban:///search?q=[prompt:搜索内容]
```

### 新浪微博

微博搜索

```
sinaweibo://searchall?q=[prompt]
```

扫一扫

```
sinaweibo://qrcode
```

发微博

```
sinaweibo://share?content=[prompt:微博内容]
```

指定用户个人资料页

```
sinaweibo://userinfo?uid=[uid]
```

### 小红书

搜索页面

```
xhsdiscover://search/recommend
```

### 美团

全局搜索

```
imeituan://www.meituan.com/search?q=[prompt:商品名称]
```

酒店搜索

```
imeituan://www.meituan.com/hotel/search?q=[prompt:酒店名称]
```

普通扫码页面

```
imeituan://www.meituan.com/scanQRCode
```

共享单车扫码，该 URL Scheme 有且仅有配合 Launch Center Pro 的 `lc-callback` 协议方能正常使用。

```
imeituan://www.meituan.com/bike/scan?lc-callback=imeituan://www.meituan.com/bike/inscan
```

### 大众点评

搜索商品

```
dianping://searchshoplist?keyword=[prompt:商品名称]
```

### 欧陆词典

```
eudic://dict/[prompt:生词]
```

### 什么值得买

搜索商品

```
smzdm://search?json={"channelName":"home","search_type":"1","keyWord":"[prompt:商品名称]"}
```

### 云支付

付款

```
upwallet://pay
```

乘车码

```
upwallet://rn/rnshcarcode
```

小程序

```
upwallet://applet?toLink=【小程序 URL 地址】&encryptAppId=【小程序 ID】
```

### 知乎

搜索问题

```
zhihu://search?q=[prompt:问题]
```

```
zhihu://zhihu.com/search?q=[prompt:问题]
```

```
zhihu://www.zhihu.com/search?q=[prompt:问题]
```

扫一扫

```
zhihu://codereader
```

### 哔哩哔哩

打开主页

```
bilibili://home
```

搜索视频

```
bilibili://search?keyword=[prompt:视频名称]
```

视频播放页面

```
bilibili://video/{av}or{bv}
```

扫一扫

```
bilibili://qrcode
```

个人中心

```
bilibili://user_center
```

UID用户页面

```
bilibili://space/{uid}
```

打开直播间

```
bilibili://live/{id}
```

我的收藏

```
bilibili://main/favorite
```

### YouTube

搜索视频，此处的 URL 在 Universal Link 的作用下会直接跳转 YouTube 客户端，如果没有安装客户端则直接打开网页搜索。

```
https://m.youtube.com/results?q=[prompt:视频名称]
```

### App Store

搜索软件

```
itms-apps://search.itunes.apple.com/WebObjects/MZSearch.woa/wa/search?media=software&term=[prompt:软件名称]
```

### 京东

扫一扫

```
openjd://virtual?params={"category":"jump","des":"saoasao"}
```

搜索商品

```
openjd://virtual?params={"des":"productList","keyWord":"[prompt:商品名称]","from":"search","category":"jump"}
```

### 拼多多

搜索商品

```
pinduoduo://com.xunmeng.pinduoduo/search_result.html?search_key=[prompt:商品名称]
```

### 微信

扫一扫

```
weixin://scanqrcode
```

### 支付宝

付款码

```
alipay://platformapi/startapp?appId=20000056
```

```
launch://x-callback-url/clipboard?text={{}}&x-success={{alipay://platformapi/startapp?appId=20000056}}
```

扫一扫

```
alipay://platformapi/startapp?appId=10000007
```

```
launch://x-callback-url/clipboard?text={{}}&x-success={{alipay://platformapi/startapp?appId=10000007}}
```

乘车码

```
alipay://platformapi/startapp?appId=200011235
```

```
launch://x-callback-url/clipboard?text={{}}&x-success={{alipay://platformapi/startapp?appId=200011235}}
```

国家政务平台扫一扫防疫信息码

```
alipays://platformapi/startapp?appId=2019011763060066&page=pages/health-code/health-scan/health-scan
```

北京健康宝扫一扫直达

```
alipays://platformapi/startapp?appId=2021001135679870&page=pages/codeScanning/index
```

麦当劳点餐页面直达

```
alipays://platformapi/startapp?appId=2017090708602953&page=product/pages/list/index?orderType=1
```

其他支付宝相关的小程序的 URL Scheme 请参照[《URL Scheme 查询指南》](https://sspai.com/post/66334)支付宝段落自行查询，此处不再一一列举。

### 菜鸟

打开身份码

```
cainiao://desktop/station_code
```

```
launch://x-callback-url/clipboard?text={{}}&x-success={{cainiao://desktop/station_code}}
```

### 钉钉

扫一扫

```
dingtalk://dingtalkclient/page/scan
```

### 飞书

扫一扫

```
feishu://applink.feishu.cn/client/qrcode/main
```

考勤打卡

```
feishu://applink.feishu.cn/client/mini_program/open?appId=cli_9c21a4767c305107
```

### Launch Center Pro

```
launch://x-callback-url/import?title=【标题】&url=【URL Scheme】
```

```
URL Scheme 需要全编码

➜ python -c "import clipboard
from urllib import parse
urls = parse.quote(clipboard.paste())
name = input('\n输入动作名称：')
print('launch://x-callback-url/import?title=' + parse.quote(name) + '&url=' + urls)"
```

根据 ID 运行动作  

```
launch://?url=[action:123]
```

### 设置

捷径屏幕使用时间通知

```
prefs:root=SCREEN_TIME&path=SCREEN_TIME_SUMMARY#DAY/com.apple.shortcuts
```

```
prefs:root=SCREEN_TIME&path=SCREEN_TIME_SUMMARY#WEEK/com.apple.shortcuts
```

```
App-prefs:SCREEN_TIME&path=SCREEN_TIME_SUMMARY#DAY/com.apple.shortcuts
```

```
App-prefs:SCREEN_TIME&path=SCREEN_TIME_SUMMARY#WEEK/com.apple.shortcuts
```

### 参考文章

[iOS 快捷指令 Shortcut 频繁弹出通知及关闭通知的 URL Scheme]