# 能做什么以及需要什么

WebServerAgent可以实现iOS的自动化测试（外挂）。

需要的条件：
iOS设备
MacOS
安装Xcode

不需要的条件：
iOS设备不需要越狱
不需要付费苹果开发者帐号

# 安装wda与配置证书

```
git clone https://github.com/facebook/WebDriverAgent
./Scripts/bootstrap.sh
```
可能要先用brew安装Carthage和node，因为bootstrap.sh脚本会使用Carthage下载所有的依赖，使用npm打包响应的js文件。

## 设置证书

用Xcode打开WebDriverAgent文件夹下的WebDriverAgent.xcodeproj这个文件。

首先进入Xcode-Preferences-Accounts，用AppleID登录，这算是一个免费的苹果开发者帐号。

已经打开WebDriverAgent后，在WebDriverAgentLib-Build Settings-Packaging下找到Product Bundle Identifier，在com.facebook.WebDriverAgentLib后面随便加点字符。

在WebDriverAgentLib-General-Signing中把Automatically manage signing点上勾，在Team中选择自己的开发者帐号，等下面的Signing Certificate配置完成。

已经打开WebDriverAgent后，在WebDriverAgentRunner-Build Settings-Packaging下找到Product Bundle Identifier，在com.facebook.WebDriverAgentRunner后面随便加点字符。

在WebDriverAgentRunner-General-Signing中把Automatically manage signing点上勾，在Team中选择自己的开发者帐号，等下面的Signing Certificate配置完成。

## 运行WDA

手机插到Mac上，手机上选择信任电脑。

Product-Scheme中选WebDriverAgentRunner，Product-Destination中选自己的手机。

Xcode中选Product-Test，开始在手机上安装文件，但第一次可能不成功，因为需要在手机上安装开发者信任文件。安装即可。貌似这一文件有效期是7天，所以过期就要再安装一遍。再次Product-Test，应该就能运行了。在View-Debug Area中点Activate Console，看到一个网址和端口，如10.0.0.1：8100。手机端会安装一个应用，且启动后消失。用手机端safari开启localhost:8100应当有json字符。

# 电脑端口向手机映射

这一步摸索半天，因为电脑打开10.0.0.1：8100或localhost:8100是没用的。

先用brew安装usbmuxd和libimobiledevice。

然后用如下命令把电脑的8100端口和手机的8100端口绑定：
```
iproxy 8100 8100 [UDID]
```
其中手机的UDID可以用iOS端Safari去 https://fir.im/udid 获取，一台机子时可以不写udid。

此时电脑打开localhost:8100应有与手机同样的json字符了。

# python应用wda

```
pip install facebook-wda
```

# 参考网页与应用

iOS真机如何安装WebDriverAgent：
https://testerhome.com/topics/7220

微信跳一跳Python，Android和iOS操作步骤：
https://www.cnblogs.com/dzpsite/p/8241113.html

Python微信《跳一跳》辅助GitHub：
https://github.com/wangshub/wechat_jump_game

