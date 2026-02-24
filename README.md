# AppletReverseTool
微信小程序逆向工具

# 欢迎点击进入我的App Store主页下载本人已上架发布的应用。
<a href='https://apps.apple.com/cn/developer/%E5%BC%BA-%E6%9B%BE/id1453461397'><img height='70' alt='Download from AppStore' src='https://img.whalenas.com:283/image/202207141215375.png' /></a>
> [https://apps.apple.com/cn/developer/%E5%BC%BA-%E6%9B%BE/id1453461397](https://apps.apple.com/cn/developer/%E5%BC%BA-%E6%9B%BE/id1453461397)
# 关注Telegram频道，获取最新信息。
> [https://t.me/iTelecast](https://t.me/iTelecast)

## 工具准备
下载地址：https://github.com/strengthen/AppletReverseTool
包含：逆向工具、解密工具
逆向工具
目前用的是：wxappUnpacker

##解密工具
先解密
网上有很多教程，是分苹果和安卓的，还要用到模拟器，其实不用那么麻烦，直接用微信PC客户端就可以了。
### 1、找到文件管理的位置
Applet 是存放小程序编译包的，
这里面存放的都是打开过的小程序包文件
### 2、打开小程序
在pc端打开一个小程序，尽可能点开所有的页面，让本地自动生成一个本地包，在刚刚设置好的文件夹里：
不过里面的是加密过的文件：APP.wxapkg就需要用到我们前面的解密软件。
### 3、解密
选择小程序的加密包，0.1秒解密成功：
加密后会存放在wxpack里面：
再逆向
正式用到开发的【wxappUnpacker】了。下面的操作，都是在cmd命令窗口中操作的，需要强调的是，必须在wxappUnpacker路径里才可以，简易方法是，直接在【wxappUnpacker】文件夹的地址栏里输入cmd即可。
#### （1）、逆向准备
打开逆向工具文件夹，直接输入cmd打开命令板：
检查是否有node环境啊！！
安装依赖，挨个执行：
npm install
npm install esprima
npm install css-tree
npm install cssbeautify
npm install vm2
npm install uglify-es
npm install js-beautify
#### （2）、正式逆向
把刚才wxpack下的解密包直接拖过来：
bingo.bat 主包路径（可以直接拖入）
编译后的文件，会保存在wxpack文件包下：
OK，编译完成，接下来直接使用微信开发工具打开，即可学习前辈们的前端设计了，骚年。
#### （3）、可能的错误
如果在执行编译命令时报：
this package is a subPackage which should be unpacked with -s=<MainDir>.
说明这个是分包，打开小程序时生成了两个.wxapkg文件，编译另一个文件即可，编译分包和主包的命令是不一样的：
node ./wuWxapkg.js 分包路径 -s=主包路径
#### （4）、如果生成的文件里不包含app.json文件
说明你找的小程序，是大神开发的，已经做了反编译的安全措施，所以解密失败，这也是我发这篇文章的目的。不过这种大神目前还是比较少见的。
