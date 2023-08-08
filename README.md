# AppletReverseTool
微信小程序逆向工具

工具准备
下载地址：https://github.com/strengthen/AppletReverseTool
包含：逆向工具、解密工具
逆向工具
目前用的是：wxappUnpacker

解密工具
先解密
网上有很多教程，是分苹果和安卓的，还要用到模拟器，其实不用那么麻烦，直接用微信PC客户端就可以了。
1、找到文件管理的位置
Applet 是存放小程序编译包的，
这里面存放的都是打开过的小程序包文件
2、打开小程序
在pc端打开一个小程序，尽可能点开所有的页面，让本地自动生成一个本地包，在刚刚设置好的文件夹里：
不过里面的是加密过的文件：APP.wxapkg就需要用到我们前面的解密软件。
3、解密
选择小程序的加密包，0.1秒解密成功：
加密后会存放在wxpack里面：
再逆向
正式用到大神开发的【wxappUnpacker】了。下面的操作，都是在cmd命令窗口中操作的，需要强调的是，必须在wxappUnpacker路径里才可以，简易方法是，直接在【wxappUnpacker】文件夹的地址栏里输入cmd即可。
1、逆向准备
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
2、正式逆向
把刚才wxpack下的解密包直接拖过来：
bingo.bat 主包路径（可以直接拖入）
编译后的文件，会保存在wxpack文件包下：
OK，编译完成，接下来直接使用微信开发工具打开，即可学习前辈们的前端设计了，骚年。
3、可能的错误
如果在执行编译命令时报：
this package is a subPackage which should be unpacked with -s=<MainDir>.
说明这个是分包，打开小程序时生成了两个.wxapkg文件，编译另一个文件即可，编译分包和主包的命令是不一样的：
node ./wuWxapkg.js 分包路径 -s=主包路径
4、如果生成的文件里不包含app.json文件
说明你找的小程序，是大神开发的，已经做了反编译的安全措施，所以解密失败，这也是我发这篇文章的目的。不过这种大神目前还是比较少见的。

## 关注Telegram频道，获取最新通知
> [https://t.me/iTelecast](https://t.me/iTelecast)

## 自己研发自己推广。欢迎点击跳转App Store安装。
### 一、iPhone/iPad端安装
>[1、iTelevision （更好用的直播流播放器/手机电视）](https://apps.apple.com/cn/app/itelevision/id6443470500)
> iTelevision群：[https://t.me/iTelevisions](https://t.me/iTelevisions)

>[2、iNFC （读写NFC标签，复制门禁卡）](https://apps.apple.com/cn/app/infc/id1562054959)
> iNFC群：[https://t.me/NFCMaster](https://t.me/NFCMaster)

>[3、iSMS （AI离线智能拦截垃圾短信）](https://apps.apple.com/cn/app/isms/id1610118657)
> iSMS群：[https://t.me/iSMS_iContact](https://t.me/iSMS_iContact)

>[4、iDraft (电子绘图、电子草稿)](https://apps.apple.com/cn/app/idraft/id1555981466)
> iDraft群：[https://t.me/iDrafts](https://t.me/iDrafts)

>[5、iBlog （博客园客户端，开发者的网上家园）](https://apps.apple.com/cn/app/iblog/id1571216825)
> iBlog群：[https://t.me/iCnblog](https://t.me/iCnblog)

>[6、iNetwork](https://t.me/iNetworka)
> iNetwork群：[https://t.me/iNetworka](https://t.me/iNetworka)
### 二、iMac、MacBook等安装：
>[1、iSpider （复原windows端的蜘蛛纸牌）](https://apps.apple.com/cn/app/spider-card/id1579985010?mt=12)

>[2、Minesweeper+（复原windows端的扫雷）](https://apps.apple.com/cn/app/minesweeper/id1576828278?mt=12)

>[3、Touch Bar Brickout （打砖块小游戏）](https://apps.apple.com/cn/app/touch-bar-brickout/id1582094533?mt=12)

>[4、Redis Pro （后端Redis工具）](https://apps.apple.com/cn/app/redis-pro/id1576996455?mt=12b)
