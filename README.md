# 超级签名实现步骤详解

### 超级签名是什么
![来源蒲公英](./蒲公英.png)
<br>
图中可以看出几个重要信息<br>
1、机制与企业签名不同<br>
2、会掉签<br>
3、同一台设备可以无限制下载次数<br>
问: 那么同时满足这三点是什么?<br>
答: 通过添加设备UDID进行安装的测试版IPA

### 如何操作
通过上文我们得出结论, 超级签名其实就是通过将设备的UDID写入到开发者后台,然后生成一个存在当前设备UDID的IPA对设备进行安装,那么就会产生以下几个问题:<br>
1、如何获取UDID <br>
2、如何将UDID写入开发者后台<br>
3、如何将带有UDID的测试证书写入到IPA<br>
4、如何安装新的IPA<br>
上面的问题我们接下来一个一个解决,首先第一个,<br>
`如何获取UDID?`<br>
这里我们依靠强大的互联网搜索技术, 找到一篇讲解如何获取UDID的文章, 那就是[天狐大佬的文章](https://github.com/shaojiankui/iOS-UDID-Safari),文章中详细的讲解了如何通过`.mobileconfig`配置文件获取设备UDID,<br>
[获取UDID测试网址](http://dev.skyfox.org/udid/)<br>
第二个问题`如何将UDID写入开发者后台`<br>
想要回答这个问题... 那就要聊到[苹果大大曾经公开的一部分接口了](https://developer.apple.com/documentation/)
![苹果开发者文档](./苹果开发者文档.png)
点进去就会发现`踏破铁鞋无觅处 得来全不费工夫`
![证书管理](./证书管理.png)
我的天... 都是英文... 这里容我说一句<h4>谷歌牛逼~~~</h4>
![谷歌牛逼](./翻译之后.png)
根据这份文档我们就可以轻松实现将UDID写入开发者后台这一步骤, [本菜鸡根据官方文档通过python实现的小demo](https://github.com/iizvv/its/blob/master/itsUtils.py)
第二个问题到此就算解决了.OK, 我们继续说第三个问题`如何将带有UDID的测试证书写入到IPA`, <h4>核心、核心、核心...</h4>这就是整个流程中最重要的环节, 然

### 如有需要可以联系我
![q q](./27481566307584_.pic.jpg)
