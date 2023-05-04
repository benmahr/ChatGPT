# 小白零基础，搭建ChatGPT、Bing等稳定畅游的外网环境


ChatGPT注册参考：[小白零基础，注册ChatGPT，充值 Plus使用GPT 4（完整教程）](https://zhuanlan.zhihu.com/p/625800667)

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

连接成功后，会出现如上图所示，之后就可以复制粘贴代码部署了。

**Ubuntu 16+ / Debian 8+ 系统 v2ray一键部署管理脚本**：

安装命令：

source <(curl -sL https://multi.netlify.app/v2ray.sh) --zh

升级命令(保留配置文件更新)：

source <(curl -sL https://multi.netlify.app/v2ray.sh) -k

卸载命令：

source <(curl -sL https://multi.netlify.app/v2ray.sh) --remove

> 如果输入安装命令后提示curl: command not found，那是因为服务器系统没有自带curl命令，安装一下curl。

> CentOS系统安装curl命令：yum install -y curl

> Debian/Ubuntu系统安装curl命令：apt-get install -y curl

> 安装完成后，输入v2ray可进入管理页面。脚本来自[Jrohy/multi-v2ray](https://github.com/Jrohy/multi-v2ray)。

------

**脚本演示**

复制上面安装命令代码到VPS服务器里，复制代码用鼠标右键的复制，然后在vps里面右键粘贴进去，因为ctrl+c和ctrl+v无效。接着输入数字1来安装。安装完成后，如果想修改、查看配置等，可以输入v2ray进行管理页面，不用重复安装脚本。

[![img](https://camo.githubusercontent.com/a0a03ac24ef5ebc478694017dd88531841ef7ae99710f724103ef5989b0eeaaa/68747470733a2f2f666173746c792e6a7364656c6976722e6e65742f67682f416c76696e393939392f5041432f76327261792f76327261792d322d312e504e47)](https://camo.githubusercontent.com/a0a03ac24ef5ebc478694017dd88531841ef7ae99710f724103ef5989b0eeaaa/68747470733a2f2f666173746c792e6a7364656c6976722e6e65742f67682f416c76696e393939392f5041432f76327261792f76327261792d322d312e504e47)

[![img](https://camo.githubusercontent.com/eb385c35ed77dfa7e692f5b755ea2868ea2d9e236e3530ce28f006614a4a51f8/68747470733a2f2f666173746c792e6a7364656c6976722e6e65742f67682f416c76696e393939392f5041432f76327261792f76327261792d322d322e504e47)](https://camo.githubusercontent.com/eb385c35ed77dfa7e692f5b755ea2868ea2d9e236e3530ce28f006614a4a51f8/68747470733a2f2f666173746c792e6a7364656c6976722e6e65742f67682f416c76696e393939392f5041432f76327261792f76327261792d322d322e504e47)

安装速度很快，安装结束后默认有个kcp协议帐号，如果不想用kcp协议，可以输入v2ray管理页面来进行传输方式的更改。（推荐websocket协议）

[![img](https://camo.githubusercontent.com/5ce90463624dc1abfd98f6facfcb266828a41fb87cc6b7fa6c5ad4bb98b43639/68747470733a2f2f666173746c792e6a7364656c6976722e6e65742f67682f416c76696e393939392f5041432f76327261792f76327261792d322d332e504e47)](https://camo.githubusercontent.com/5ce90463624dc1abfd98f6facfcb266828a41fb87cc6b7fa6c5ad4bb98b43639/68747470733a2f2f666173746c792e6a7364656c6976722e6e65742f67682f416c76696e393939392f5041432f76327261792f76327261792d322d332e504e47)

[![img](https://camo.githubusercontent.com/3781abd3c7663b7acabba2ab90098c8e08b837b19760d9554f7648e775ae152a/68747470733a2f2f666173746c792e6a7364656c6976722e6e65742f67682f416c76696e393939392f5041432f76327261792f76327261792d322d342e504e47)](https://camo.githubusercontent.com/3781abd3c7663b7acabba2ab90098c8e08b837b19760d9554f7648e775ae152a/68747470733a2f2f666173746c792e6a7364656c6976722e6e65742f67682f416c76696e393939392f5041432f76327261792f76327261792d322d342e504e47)

[![img](https://camo.githubusercontent.com/2f9f2917b069a8d36c75a5e76e7373410c012d1f058cfa890aa85497b942075d/68747470733a2f2f666173746c792e6a7364656c6976722e6e65742f67682f416c76696e393939392f706163322f736f6674696d61672f76327261792d63732e706e67)](https://camo.githubusercontent.com/2f9f2917b069a8d36c75a5e76e7373410c012d1f058cfa890aa85497b942075d/68747470733a2f2f666173746c792e6a7364656c6976722e6e65742f67682f416c76696e393939392f706163322f736f6674696d61672f76327261792d63732e706e67)

**注意：如果安装后提示“Failed to start V2Ray Service”，即v2ray无法启动成功，输入以下3条命令**：

> sed -i "s/v2ray -config/v2ray run -config/g" /etc/systemd/system/v2ray.service.d/10-donot_touch_single_conf.conf

> systemctl daemon-reload

> systemctl restart v2ray

如果以上命令还是无法启动，将服务器的v2ray版本退回到指定版本，输入命令：

> v2ray update v4.45.2

> 之后再重启下v2ray就可以了: 输入命令v2ray--数字1服务管理--数字3重启服务





### 优化 V2Ray

五合一的TCP网络加速脚本，包括了BBR原版、BBR魔改版、暴力BBR魔改版、BBR plus（首选）、Lotsever(锐速)安装脚本。可用于KVMXen架构，不兼容OpenVZ（OVZ）。支持Centos 6+ / Debian 7+ / Ubuntu 14+，BBR魔改版不支持Debian 8。

------

wget -N --no-check-certificate "https://raw.githubusercontent.com/chiakge/Linux-NetSpeed/master/tcp.sh"

chmod +x tcp.sh

./tcp.sh

------

> 如果提示 wget: command not found 的错误，这是你的系统精简的太干净了，wget都没有安装，所以需要安装wget。CentOS系统安装wget命令： yum install -y wget Debian/Ubuntu系统安装wget命令：apt-get install -y wget

安装完成后，脚本管理命令为：./tcp.sh

[![img](https://camo.githubusercontent.com/43d455bfc441847cd05d216041bc06878ae6ec8fe6053105d1f6841ab00a767f/68747470733a2f2f666173746c792e6a7364656c6976722e6e65742f67682f416c76696e393939392f706163322f76756c74722f6e6577626272312e6a7067)](https://camo.githubusercontent.com/43d455bfc441847cd05d216041bc06878ae6ec8fe6053105d1f6841ab00a767f/68747470733a2f2f666173746c792e6a7364656c6976722e6e65742f67682f416c76696e393939392f706163322f76756c74722f6e6577626272312e6a7067)

操作方法：先安装内核，重启vps让内核生效，再启动对应的加速即可。数字1的BBR/BBR魔改内核对应数字4、5、6的BBR加速、BBR魔改加速和暴力BBR魔改版加速。数字2的BBRplus内核对应数字7的BBRplus加速。数字3的锐速加速内核对应数字8的锐速加速。

以安装暴力BBR魔改版加速为例，我们先安装对应的内核，输入数字1

[![img](https://camo.githubusercontent.com/9cdf5aca624bea0c8e7f4febad3dfb50856004ee0a4bf516a1da9fefe01db5e1/68747470733a2f2f666173746c792e6a7364656c6976722e6e65742f67682f416c76696e393939392f706163322f76756c74722f6e6577626272322e6a7067)](https://camo.githubusercontent.com/9cdf5aca624bea0c8e7f4febad3dfb50856004ee0a4bf516a1da9fefe01db5e1/68747470733a2f2f666173746c792e6a7364656c6976722e6e65742f67682f416c76696e393939392f706163322f76756c74722f6e6577626272322e6a7067)

内核安装完成后，输入y进行重启，重启才能让内核生效

[![img](https://camo.githubusercontent.com/640a029001c8574b912dfd7628af064bf11b20a8d9ad3850c7885baa728f468e/68747470733a2f2f666173746c792e6a7364656c6976722e6e65742f67682f416c76696e393939392f706163322f76756c74722f6e6577626272332e6a7067)](https://camo.githubusercontent.com/640a029001c8574b912dfd7628af064bf11b20a8d9ad3850c7885baa728f468e/68747470733a2f2f666173746c792e6a7364656c6976722e6e65742f67682f416c76696e393939392f706163322f76756c74722f6e6577626272332e6a7067)

重启完成后，输入数字6来启动暴力BBR魔改版加速

[![img](https://camo.githubusercontent.com/10ce2b1df7a5d83940836cc4211765eedc2f971a3afeb7ee54f9e05bb34f9395/68747470733a2f2f666173746c792e6a7364656c6976722e6e65742f67682f416c76696e393939392f706163322f76756c74722f6e6577626272342e6a7067)](https://camo.githubusercontent.com/10ce2b1df7a5d83940836cc4211765eedc2f971a3afeb7ee54f9e05bb34f9395/68747470733a2f2f666173746c792e6a7364656c6976722e6e65742f67682f416c76696e393939392f706163322f76756c74722f6e6577626272342e6a7067)

[![img](https://camo.githubusercontent.com/b73fea955aaf98f08162d9a8872d1c79fbce2aef852c084745a84771d305240b/68747470733a2f2f666173746c792e6a7364656c6976722e6e65742f67682f416c76696e393939392f706163322f76756c74722f6e6577626272352e6a7067)](https://camo.githubusercontent.com/b73fea955aaf98f08162d9a8872d1c79fbce2aef852c084745a84771d305240b/68747470733a2f2f666173746c792e6a7364656c6976722e6e65742f67682f416c76696e393939392f706163322f76756c74722f6e6577626272352e6a7067)

输入./tcp.sh查看最终是否启动成功。

如果想换一个加速，输入数字9进行卸载加速，然后进行同样的操作，安装内核再安装对应内核的加速即可。

**注意：如果在安装内核环节出现这样一张图，注意选择NO**

[![img](https://camo.githubusercontent.com/4d9ba113a7a4c183432be250722657af50b009924206005ab97a2be14e5ba36f/68747470733a2f2f666173746c792e6a7364656c6976722e6e65742f67682f416c76696e393939392f706163322f76756c74722f6e6577626272362e6a7067)](https://camo.githubusercontent.com/4d9ba113a7a4c183432be250722657af50b009924206005ab97a2be14e5ba36f/68747470733a2f2f666173746c792e6a7364656c6976722e6e65742f67682f416c76696e393939392f706163322f76756c74722f6e6577626272362e6a7067)



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





**常见问题参考解决方法**：

**1、账号无法使用，可能原因一：客户端与服务端的设备系统时间相差过大。**

**a、一般国外的VPS的镜像都是默认的国外时区，使用起来不是很方便。可以把它修改成北京时间，就会方便很多。** **修改中国时区代码如下**：

\cp -f /usr/share/zoneinfo/Asia/Shanghai /etc/localtime

**b、利用NTP同步时间协议**

**CentOS系统先安装NTP**：yum install ntp ntpdate -y

> 如果是Ubuntu/Debian系统执行下面2条命令来安装NTP

> apt-get update

> apt-get install ntp ntpdate -y

**安装NTP后，按照顺序依次执行以下3条命令，分别是停止NTP服务、同步NTP时间、启动NTP服务**：

service ntpd stop

ntpdate us.pool.ntp.org

service ntpd start

**执行完成后，VPS上就是相对精确的时间设置了。很多依赖于系统时间的应用程序也就能正常工作了。注意：当vps重启后输入date来检查下时间，如果时间不是最新的，再执行以上3条命令即可。**

> 除了通过NTP来同步时间以外，还可以手动修改vps系统时间，需要先修改中国时区，之后输入时间命令，格式（数字改为和自己电脑时间一致，误差30秒以内）：date -s "2020-2-02 19:14:00"

**2、账号无法使用，可能原因：vps防火墙端口没有放开或者本地电脑防火墙、杀毒软件阻挡代理软件。**

关闭vps防火墙即可开放所有端口，本地电脑防火墙和杀毒软件手动关闭即可。

查看防火墙状态命令：firewall-cmd --state

停止firewall命令：systemctl stop firewalld.service

禁止firewall开机启动命令：systemctl disable firewalld.service

**3、搭建的账号之前能用，突然不能用了，怎么解决？**

**如果ip不能ping通，xshell不能直接连接vps服务器，说明ip被墙了，需要开新服务器换ip。**

**如果ip能ping，xshell能直接连接vps服务器，说明ip没有被墙，多半是端口被封了，优先换端口。**

**如果ip和端口都没问题，可以尝试来更换传输协议，比如Websocket、TCP、mKCP等，测试哪种协议最适合自己的网络环境。**

