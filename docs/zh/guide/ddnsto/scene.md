
**此版块，主要说一些ddnsto的更多玩法，有很多朋友们，玩出了很多新花样，所以归纳一些比较常用的。**

## 远程穿透易有云网页端

易有云网页端也可以利用DDNSTO远程穿透访问。

1.首先保证DDNSTO和易有云在同一网络，不一定在同一个设备上，然后DDNSTO控制台添加易有云网页端域名；

   ![scene](./scene/linease1.jpg)

ps：输入IP地址时记得带上易有云的端口8897。

   ![scene](./scene/linease2.jpg)
   
2.然后就可以用过域名远程访问易有云网页端了。


## 远程穿透Jellyfin

Jellyfin是一个自由的软件媒体系统，用于控制和管理媒体和流媒体。

现在伙伴们的设备多样化性能也很强悍，所以有些伙伴部署了Jellyfin，打造个人媒体中心。那么我们也来穿透下，做成能远程能外网访问的个人媒体中心。

1.直接开始设置ddnsto，注意端口，若没有改默认端口那就是8096；
   ![scene](./scene/Jellyfin1.jpg)

2.这样我们就能畅快的远程浏览个人媒体中心了。

   ![scene](./scene/Jellyfin2.jpg)
   
###  穿透Jellyfin APP

Jellyfin是有APP的，也能远程穿透，设置非常简单；

1.先进行ddnsto身份验证：

A：如果是在外网(指不是和群晖设备在同一局域网或者蜂窝数据下)，需要[身份验证](https://www.ddnsto.com/zh/guide/Authentication.html)。

B：如果在同一局域网下，不用验证ddnsto身份。

2.然后直接输入之前设置ddnsto穿透网址(去掉尾部端口)，回车即可穿透Jellyfin。

   ![scene](./scene/Jellyfin3.jpg)

   
   
## 远程pve控制

基本现在很多人的小主机都是性能强悍的，通过通过PVE或者ESXI来安装各种系统(OpenWrt、iKuai、docker等)，只要通过PVE或者EXSI安装的OpenWrt/docker/LEDE等，部署好了ddnsto，那就就能远程访问PVE或者ESXI的管理界面。

   ![scene](./scene/scene-pve1.jpeg)
   
1.ddnsto设置好穿透，注意网址和端口即可。

PS：比如pve是https，别写成http了。

   ![scene](./scene/scene-pve2.jpeg)
   
2. 很简单的步骤，就能畅快的远程管理PVE了。

   ![scene](./scene/scene-pve3.jpeg)
    
## qBittorrent远程下载

#### 注意： 如页面显示unauthorized，请在域名后加上“/”

1.qBittorrent，一款bt下载插件，是能通过ddnsto远程控制的，注意下端口。

   ![scene](./scene/scene-qb1.jpeg)
   
2.打开WEB管理界面，设置——WebUI——“取消”启用跨站请求伪造(CSRF)保护。

PS：此选项需要取消，不然后面ddnsto可能连不上。
   
   ![scene](./scene/scene-qb4.jpeg)
   
3.设置好qBittorrent的ddnsto远程穿透。

   ![scene](./scene/scene-qb2.jpeg)

4.就能畅快的远程bt下载。

   ![scene](./scene/scene-qb3.jpeg)  
   
## Transmission远程下载

1.Transmission也是一款bt下载插件，也能通过ddnsto控制。

   ![scene](./scene/scene-tm1.jpeg)
   
2.设置好Transmission的ddnsto远程穿透。
   
   ![scene](./scene/scene-tm2.jpeg)
   
3.畅快的远程bt下载吧。 
 
   ![scene](./scene/scene-tm3.jpeg)
   
## 百度云远程下载

1.BaiduPCS-Web是一款可以下载百度云的插件，也能通过ddnsto控制。

   ![scene](./scene/scene-bdy1.jpeg)
   
2.设置好BaiduPCS-Web的ddnsto远程穿透。
   
   ![scene](./scene/scene-bdy2.jpeg)
   
3.畅快的远程下载百度云吧。 
 
   ![scene](./scene/scene-bdy3.jpeg)  
   

## 远程登录财务软件（软件是网页版登录本地服务）

畅捷通是一款财务一站式管理平台，可以通过ddnsto远程控制。

 ![scene](./scene/scene-cw2.jpg)  

 1.[windows电脑安装ddnsto客户端](https://fw.koolcenter.com/binary/ddnsto/pc/ddnsto-win.zip)

 ![scene](./scene/scene-cw4.jpg)  

 3.设置好畅捷通的ddnsto远程穿透。

  ![scene](./scene/scene-cw3.jpg)  

3.远程登入财务软件。

 ![scene](./scene/scene-cw1.jpg)  

 ## 远程访问可道云

 可道云是一款快捷高效的私有云和在线文档管理系统。也能通过ddnsto控制。

1.设置好可道云的ddnsto远程穿透。

 ![scene](./scene/kedaoyun1.jpg)  

2.远程成功访问可道云。

![scene](./scene/kedaoyun2.jpg)  

### 问题：用https远程访问可道云不成功

![scene](./scene/kedaoyun3.jpg)  

#### 解决方法：可道云需要配置一下才能用ddnsto的https远程访问

- 在站点下 ./config 目录新建一个文件 ./config/define.php指定https访问地址 (改了之后只能用这个地址访问)

![scene](./scene/kedaoyun5.jpg)  

- 现在用https开头可以访问

![scene](./scene/kedaoyun4.jpg)  

## 通过VNC远程控制Windows电脑桌面

#### 被控Windows电脑下载VNC并设置
这里推荐大家使用TigerVNC（因为TigerVNC是免费使用的）

我们来到TigerVNC的官网：
<a href="https://tigervnc.org/">https://tigervnc.org/</a>



在Downloads拦下点击进入GitHub下载

![vnc](./vnc/1.png)  

通过二进制文件链接下载

![vnc](./vnc/2.png)  

选择Windows 64位的VNC下载

![vnc](./vnc/3.png)  

下载完成后，运行VNC程序  

选择安装路径一直点击下一步就可以了。

打开TigerVNC，点击Properties

![vnc](./vnc/4.png)  

然后点击Configure

![vnc](./vnc/5.png)  


设置VNC密码

![vnc](./vnc/6.png)  

点击应用、确定

![vnc](./vnc/7.png)  

这样就设置好VNC了。

如果是用RealVNC 的用户，

需要勾选允许旧版本的客户端访问。

![vnc](./vnc/11.png)  

#### 通过DDNSTO远程应用的远程VNC来远程控制电脑桌面
点击远程应用，点击添加

![vnc](./vnc/8.png) 

选择远程VNC
应用名称可以随便填；
IP填被控电脑的IP地址；
端口不变；
用户名可以不填；
密码填被控电脑VNC的密码；
点击保存。

![vnc](./vnc/9.png) 

就可以通过DDNSTO来远程控制Windows电脑桌面了。

![vnc](./vnc/10.png) 



