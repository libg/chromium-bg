# chromium-bg
my repository for chromium code manager

关于chromium源码下载及编译问题那些事

参考官网介绍文档
https://chromium.googlesource.com/chromium/src/+/main/docs/windows_build_instructions.md

首先需要有稳定且快速的vpn，我用的是shadowsocks，自己搭建vps也可以，推荐TX的CVM。

然后搭建好开发环境，接下来就是设置相关工具的代理。

一、设置代理
1、设置cmd代理
   1.1 将vpn代理模式设置为全局模式；
   1.2 管理员打开cmd，输入如下指令：
        >netsh
        netsh>winhttp
        netsh winhttp>set proxy 127.0.0.1:1080
2、设置http代理
   2.1 在cmd中输入：
       >set http_proxy=http://127.0.0.1:1080
       >set https_proxy=http://127.0.0.1:1080
       >set socks5_proxy=socks5://127.0.0.1：1080
4、设置git代理
   4.1 使用http/https代理服务器，在cmd中输入：
       >git config --global http.proxy "http_proxy"
       >git config --global https.proxy %https_proxy%
   4.2 使用socks5代理服务器
       >git config --global http.proxy %socks5_proxy%
       >git config --global https.proxy %socks5_proxy%
   4.3 验证查看代理
       >git config --get http.proxy
       >git config --get https.proxy
5、设置boto代理
   5.1 创建.boto文件，内容如下：
       [Boto]
       proxy = 127.0.0.1
       proxy_port = 1080
   5.2 在cmd中输入: >set NO_AUTH_BOTO_CONFIG=filepath\.boto

二、源码下载


三、源码编译


四、拉取分支

五、注意事项



