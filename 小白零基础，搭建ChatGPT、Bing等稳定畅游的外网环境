# 小白零基础，搭建ChatGPT、Bing等稳定畅游的外网环境



## **1  V2Ray简介**

#### **什么是V2Ray**

Project V 提供了单一的内核和多种界面操作方式。内核（V2Ray）用于实际的网络交互、路由等针对网络数据的处理，而外围的用户界面程序提供了方便直接的操作流程，简单来说，V2Ray就是一个代理软件，可以用来科学上网学习国外先进科学技术。

#### **V2Ray与Shadowsocks区别**

V2Ray是在Shadowsocks的作者被请喝茶之后出现的一个开源项目，目的就是为了更好的科学上网。相比于ss，V2Ray的定位是一个平台，任何开发者都可以在这个平台上利用V2Ray开发出一个新的代理软件，简单来说，ss的定位比较简单，功能也比较单一，而V2Ray的功能非常强大，相对的，V2Ray的**配置就会复杂很多**，喜欢鼓捣的同学可以试试。

#### **V2Ray的优势**

> - **更完善的协议:** V2Ray 使用了新的自行研发的 VMess 协议，改正了 Shadowsocks 一些已有的缺点，更难被墙检测到（不保证可靠性）
> - **更强大的性能:** 网络性能更好，具体数据可以看 V2Ray 官方博客
> - **更丰富的功能:**
>
> 以下是部分 V2Ray 的功能
>
> - mKCP: KCP 协议在 V2Ray 上的实现，不必另行安装 kcptun
> - 动态端口：动态改变通信的端口，对抗对长时间大流量端口的限速封锁
> - 路由功能：可以随意设定指定数据包的流向，去广告、反跟踪都可以
> - 传出代理：看名字可能不太好理解，其实差不多可以称之为多重代理。类似于 Tor 的代理
> - 数据包伪装：类似于 Shadowsocks-rss 的混淆，另外对于 mKCP 的数据包也可伪装，伪装常见流量，令识别更困难
> - WebSocket 协议：可以 PaaS 平台搭建V2Ray，通过 WebSocket 代理。也可以通过它使用 CDN 中转，抗封锁效果更好
> - Mux:多路复用，进一步提高科学上网的并发性能





## **2  优惠购买云服务器vultr**



在搭建之前需要一台境外的云服务器，而 [vultr](https://www.vultr.com/?ref=9443495-8H) 服务商比较稳定，安全，相当于境内的阿里云。

值得说的一点是， [vultr](https://www.https://www.vultr.com/?ref=9443495-8H) 给新用户的福利相当给力，充值 10 美元就可以获取 100 美元，你可以点击 [vultr 专属赠送新用户 100 美元](https://www.vultr.com/?ref=9443495-8H) 进去抢先注册。

右上角有注册按钮，你也可以切换成中文界面：

[
![vpn搭建教程](https://user-images.githubusercontent.com/84239400/119019442-be0cc500-b98c-11eb-895b-0d6300dce93d.png)](https://user-images.githubusercontent.com/84239400/119019442-be0cc500-b98c-11eb-895b-0d6300dce93d.png)

[![img](https://user-images.githubusercontent.com/84239400/119019760-0d52f580-b98d-11eb-9837-aba0990f1dfb.png)](https://user-images.githubusercontent.com/84239400/119019760-0d52f580-b98d-11eb-9837-aba0990f1dfb.png)

接着使用邮箱和密码就可以注册了。

[![img](https://user-images.githubusercontent.com/84239400/119020042-4ee3a080-b98d-11eb-8341-bfc30f4b103c.png)](https://user-images.githubusercontent.com/84239400/119020042-4ee3a080-b98d-11eb-8341-bfc30f4b103c.png)

进去之后你可以看到这个页面，说明你已经获得了 100 美元赠送的资格：

[![img](https://user-images.githubusercontent.com/84239400/119020173-733f7d00-b98d-11eb-8ecc-a1afeb556fe6.png)](https://user-images.githubusercontent.com/84239400/119020173-733f7d00-b98d-11eb-8ecc-a1afeb556fe6.png)

现在你只要选择支付宝充值 10 美元以上，就可以获得额外赠送的 100 美元。

[![img](https://user-images.githubusercontent.com/84239400/119020280-966a2c80-b98d-11eb-9113-8f5f0b75c5ea.png)](https://user-images.githubusercontent.com/84239400/119020280-966a2c80-b98d-11eb-9113-8f5f0b75c5ea.png)

接下来就可以在这个平台选购云服务器了。

点击页面左边菜单栏的 「Products」进入服务器选购页面。

### Choose Server 选择服务器

选择 Cloud Compute 即可：

[![img](https://user-images.githubusercontent.com/84239400/119020373-af72dd80-b98d-11eb-8478-02d735b82709.png)](https://user-images.githubusercontent.com/84239400/119020373-af72dd80-b98d-11eb-8478-02d735b82709.png)

### Server Location

服务器的位置，可以选择美国地区，比如纽约：

[![img](https://user-images.githubusercontent.com/84239400/119020467-cadde880-b98d-11eb-8927-d3d837bbc20c.png)](https://user-images.githubusercontent.com/84239400/119020467-cadde880-b98d-11eb-8927-d3d837bbc20c.png)

### Server Type

服务器类型，CentOS 8 x64 系统：

[![vpn搭建教程](https://user-images.githubusercontent.com/84239400/119020720-198b8280-b98e-11eb-9df3-19bf5a187a1e.png)](https://user-images.githubusercontent.com/84239400/119020720-198b8280-b98e-11eb-9df3-19bf5a187a1e.png)

### Server Size

内存，个人使用10G完全够用，这里选择3.5美元一个月，性价比高，注意不要选择IPv6 ONLY的，要不然无法搭建使用。

[![vpn搭建教程](https://user-images.githubusercontent.com/84239400/119020895-4a6bb780-b98e-11eb-9ac8-3cdd4f4397de.png)](https://user-images.githubusercontent.com/84239400/119020895-4a6bb780-b98e-11eb-9ac8-3cdd4f4397de.png)

选择完了之后，下面的其它东西都不需要填，直接点击右下角 Deploy Now 就可以了：

[![img](https://user-images.githubusercontent.com/84239400/119020981-68391c80-b98e-11eb-9f16-00c75de88eeb.png)](https://user-images.githubusercontent.com/84239400/119020981-68391c80-b98e-11eb-9f16-00c75de88eeb.png)

这时候你就拥有了自己的一台云服务器了：

[![VPN搭建教程](https://user-images.githubusercontent.com/84239400/119021075-86068180-b98e-11eb-82a9-71edb9934f23.png)](https://user-images.githubusercontent.com/84239400/119021075-86068180-b98e-11eb-82a9-71edb9934f23.png)

点击 Cloud Instance ，可以看到你服务器的 IP 地址和密码：

[![vpn搭建教程](https://user-images.githubusercontent.com/84239400/119021183-a20a2300-b98e-11eb-8ff4-7f18d3e3bb80.png)](https://user-images.githubusercontent.com/84239400/119021183-a20a2300-b98e-11eb-8ff4-7f18d3e3bb80.png)



## **3  远程连接vultr VPS**

首先你需要通过 SSH 连接 vultr 的 VPS，连接  VPS 需要使用 SSH 工具，这里推荐使用 Xshell 可以复制粘贴命令，Xshell 本身是需要付款的，作为中国人当然是使用 XX 版了，这里提供下载包如下所示：

Xshell 下载地址：https://pan.baidu.com/s/1v7RCM0IjZGn_q5aWS1WXWg，提取码: q3jw

下载后解压安装即可。

#### 使用 Xshell 连接 Linux VPS

1、打开 Xshell，点击左上角“文件”-“新建”，打开连接弹出库。

![Xshell连接VPS](https://camo.githubusercontent.com/eee8534da0fa174252bf0fc0f4dab899a4a48a3b6044e1c1462407051fc92554/68747470733a2f2f696d67323031382e636e626c6f67732e636f6d2f626c6f672f313736353439362f3230323030322f313736353439362d32303230303231383132343234343731332d313634373030333539312e6a7067)

2、在 Xshell 弹出框中输入 IP 和端口，端口一般是 22 默认，然后点击确认按钮，如下图所示：

![Xshell连接VPS](https://camo.githubusercontent.com/e5e0c22f6532d962663bb4043e027c8135ee4dd261b2240dfe1b10818b0b1217/68747470733a2f2f696d67323031382e636e626c6f67732e636f6d2f626c6f672f313736353439362f3230323030322f313736353439362d32303230303231383132343235303732302d3330303333303039322e6a7067)

3、然后输入用户名 root，勾选记住用户名。

![Xshell连接VPS](https://camo.githubusercontent.com/8100e26da58653b726d97c4d6764d4f95d41f6bf2789128037f6992ac2c7bef0/68747470733a2f2f696d67323031382e636e626c6f67732e636f6d2f626c6f672f313736353439362f3230323030322f313736353439362d32303230303231383132343235333136312d313234303735393431302e6a7067)

4、然后输入密码，勾选记住密码，点击确定。

![img](https://camo.githubusercontent.com/d8c7466c0fc3e8df5b90b388b0e4e3b58969b3d61d00acbc47819e7454eab32f/68747470733a2f2f696d67323031382e636e626c6f67732e636f6d2f626c6f672f313736353439362f3230323030322f313736353439362d32303230303231383132343235373234332d3339323939393332312e6a7067)

完成以上步骤后就可以看到连接成功的界面，如下图所示：

![img](https://camo.githubusercontent.com/bd67dd257edcfbb88e3798c3c8e261ca50f9bc6455bfaf37d6680e7bf3a978a8/68747470733a2f2f696d67323031382e636e626c6f67732e636f6d2f626c6f672f313736353439362f3230323030322f313736353439362d32303230303231383132343331343736362d313634393931393432382e6a7067)



## 4  VPS一键脚本搭建V2Ray

在上图的待输入内容处，粘贴下面的命令（复制下面的命令，然后在 Xshell 待输入内容处“鼠标右键”/“粘贴”即可）：

在上图的待输入内容处，粘贴下面的命令（复制下面的命令，然后在 Xshell 待输入内容处“鼠标右键”/“粘贴”即可）：

```
bash <(curl -s -L https://git.io/v2ray.sh)
```

> 如果提示 curl: command not found ，那是因为你的 VPS 没装 Curl ubuntu/debian 系统安装 Curl 方法: `apt-get update -y && apt-get install curl -y` centos 系统安装 Curl 方法: `yum update -y && yum install curl -y` 安装好 curl 之后就能安装脚本了

然后选择安装，即是输入 1 回车

选择传输协议，如果没有特别的需求，使用默认的 TCP 传输协议即可，直接回车

选择端口，如果没有特别的需求，使用默认的端口即可，直接回车

是否屏蔽广告，除非你真的需要，一般来说，直接回车即可

![](C:\Users\hn\Desktop\微信图片_20230429144149.png)

是否配置 Shadowsocks ，如果不需要就直接回车，否则就输入 Y 回车

Shadowsocks 端口，密码，加密方式这些东西自己看情况配置即可，我个人当然是全部直接回车

OK，按回车继续

![](C:\Users\hn\Desktop\微信图片_20230429144309.png)

安装信息，如果确保没有什么问题了，按回车继续

![](C:\Users\hn\Desktop\微信图片_20230429144355.png)

OK，出现这个界面就表示 V2Ray 已经安装完成了。

![](C:\Users\hn\Desktop\微信图片_20230429144446.png)

如上图所示，V2Ray 配置信息，Shadowsocks 配置信息都有了

如果你使用过 Shadowsocks ，那么现在你可以测试一下 Shadowsocks 配置了，看看是否能正常使用。

如果你使用过 V2Ray 某些客户端，那么现在也可以测试一下配置了。

(备注，可能某些 V2Ray 客户端的选项或描述略有不同，但事实上，上面的 V2Ray 配置信息已经足够详细，由于客户端的不同，请对号入座。)

### 优化 V2Ray

由于本人的脚本在 Debian9 系统会自动开启 BBR 优化加速了，所以不需要再安装 BBR 优化了，如果你是使用其他商家的 VPS 并且是按照此教程流程来安装 V2Ray 的话，那么你可以输入

```
v2ray bbr
```

回车，然后选择安装 BBR 或者 锐速 来优化 V2Ray

只是还想再啰嗦一下，如果你是使用国际大厂的 VPS，并且是按照此教程流程来安装 V2Ray 的话，请自行在安全组 (防火墙) 开放端口和 UDP 协议 (如果你要使用含有 mKCP 的传输协议)



# 5  V2Ray客户端配置

下载地址：[客户端](https://github.com/v2ray/v2ray-core/releases)

对`v2ray-windows-64.zip`进行解压，然后将下载的`V2RayN.exe`复制到解压后的目录，即两个下载好的文件需要在同一目录。

![V2Ray客户端配置](https://camo.githubusercontent.com/7e6ad47fef214162ebd1015de49c911b500d7f18b387735f31c2ab5b8cb56420/68747470733a2f2f696d67323031382e636e626c6f67732e636f6d2f626c6f672f313736353439362f3230323030322f313736353439362d32303230303231383132343435353838312d3739393439363530332e6a7067)

**配置**

运行 V2RayN.exe，然后进行配置。

客户端的配置需要根据你的服务端进行相应的配置，因为你的服务端协议可能是 vmess,shadowsocks 等。

如果你的服务端配置是协议 vmess，则配置如下：

![V2ray客户端配置](https://camo.githubusercontent.com/8911904bf0fec43b19ecb31b1ffbc3a90441095c9cffe10f3341b6cc4cbe83e6/68747470733a2f2f696d67323031382e636e626c6f67732e636f6d2f626c6f672f313736353439362f3230323030322f313736353439362d32303230303231383132343530343330382d3230323537373735322e6a7067)

![img](https://camo.githubusercontent.com/fe600370692df8ad1acadaaa4745f356e60c77f11a022a54aa93bba4ec936169/68747470733a2f2f696d67323031382e636e626c6f67732e636f6d2f626c6f672f313736353439362f3230323030322f313736353439362d32303230303231383132343530373033382d313630393738313530382e6a7067)

![img](https://camo.githubusercontent.com/e289e32bac11706a60cbe88a0713d8d758587b0909689d7ba876ca34192c9f54/68747470733a2f2f696d67323031382e636e626c6f67732e636f6d2f626c6f672f313736353439362f3230323030322f313736353439362d32303230303231383132343531303037372d313433323736313135352e6a7067)



## 6  避开Openai封IP的设置（稳定畅游ChatGPT的关键）

访问chatGPT的时候提示1020的错误。但是账号是正常的。

![image-20230429145956364](C:\Users\hn\AppData\Roaming\Typora\typora-user-images\image-20230429145956364.png)

解决办法： 在Xshell 里使用 cloudflare warp 封装一下。

1、bash <(curl -fsSL git.io/warp.sh) menu

![img](https://img-blog.csdnimg.cn/img_convert/93bfad675715b1e338a5fe2f690cca35.png)

选择4，安装wireGuard（如果状态显示未运行，请重置浏览器重试即可）

2、 bash <(curl -fsSL git.io/warp.sh) menu

选择5，自动配置IPv4

参考：[Cloudflare WARP 一键安装脚本 使用教程 - P3TERX ZONE](https://p3terx.com/archives/cloudflare-warp-configuration-script.html)

至此可以稳定畅游ChatGPT。

