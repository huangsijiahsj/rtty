# rtty - 在任何地方通过Web访问您的设备的终端

[1]: https://img.shields.io/badge/license-MIT-brightgreen.svg?style=plastic
[2]: /LICENSE
[3]: https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=plastic
[4]: https://github.com/zhaojh329/rtty/pulls
[5]: https://img.shields.io/badge/Issues-welcome-brightgreen.svg?style=plastic
[6]: https://github.com/zhaojh329/rtty/issues/new
[7]: https://img.shields.io/badge/release-7.1.0-blue.svg?style=plastic
[8]: https://github.com/zhaojh329/rtty/releases
[9]: https://travis-ci.org/zhaojh329/rtty.svg?branch=master
[10]: https://travis-ci.org/zhaojh329/rtty

[![license][1]][2]
[![PRs Welcome][3]][4]
[![Issue Welcome][5]][6]
[![Release Version][7]][8]
[![Build Status][9]][10]

[Xterm.js]: https://github.com/xtermjs/xterm.js
[libev]: http://software.schmorp.de/pkg/libev.html
[openssl]: https://github.com/openssl/openssl
[mbedtls(polarssl)]: https://github.com/ARMmbed/mbedtls
[CyaSSl(wolfssl)]: https://github.com/wolfSSL/wolfssl
[vue]: https://github.com/vuejs/vue
[iview]: https://github.com/iview/iview
[服务端]: https://github.com/zhaojh329/rttys

![](https://raw.githubusercontent.com/zhaojh329/rtty/doc/rtty.png)
![](https://raw.githubusercontent.com/zhaojh329/rtty/doc/screen.gif)
![](https://raw.githubusercontent.com/zhaojh329/rtty/doc/file.gif)

它由客户端和[服务端]组成。客户端采用纯C实现。[服务端]采用GO语言实现，前端界面采用[iview]和[vue]实现。

您可以在任何地方通过Web访问您的设备的终端。通过设备ID来区分您的不同的设备。

rtty非常适合远程维护您的或者您的公司的部署在全球各地的成千上万的Linux设备。

# 特性
* 部署简单，使用方便
* 根据设备ID访问不同的设备
* 提供dashboard，直观的展示在线设备
* 基于[Xterm.js]的全功能终端
* 支持传输文件
* 支持SSL: openssl, mbedtls, CyaSSl(wolfssl)
* 支持设备认证
* 支持远程执行命令
* 客户端非常小，适合嵌入式Linux

# 客户端依赖
* [libev] - 高性能的事件循环库
* [mbedtls(polarssl)]、[CyaSSl(wolfssl)]或者[openssl] - 如果您需要支持SSL

# [部署服务端](https://github.com/zhaojh329/rttys/blob/master/README_ZH.md)

# 如何安装和运行rtty客户端
## 针对Linux发行版：Ubuntu, Debian, ArchLinux, Centos
安装

    wget -qO- https://raw.githubusercontent.com/zhaojh329/rtty/master/tools/install.sh | sudo bash

查看命令行选项

    Usage: rtty [option]
        -I, --id=string          Set an ID for the device(Maximum 63 bytes, valid
                                 character:letter, number, underline and short line)
        -h, --host=string        Server's host or ipaddr(Default is localhost)
        -p, --port=number        Server port(Default is 5912)
        -d, --description=string Adding a description to the device(Maximum 126 bytes)
        -a                       Auto reconnect to the server
        -s                       SSL on
        -D                       Run in the background
        -t, --token=string       Authorization token
        -f username              Skip a second login authentication. See man login(1) about the details
        -R                       Receive file
        -S file                  Send file
        -v, --verbose            verbose
        -V, --version            Show version
        --help                   Show usage

运行RTTY(将下面的参数替换为您自己的参数)

    sudo rtty -I 'My-device-ID' -h 'your-server' -p 5912 -a -v -s -d 'My Device Description'

如果您的rttys配置了一个token，请加上如下参数（将下面的token替换为您自己生成的）

    -t 34762d07637276694b938d23f10d7164

## [如何在OpenWRT中使用](/OPENWRT_ZH.md)

## [其它嵌入式Linux平台](/CROSS_COMPILE.md)

# 如何使用
使用您的Web浏览器访问您的服务器: `https://your-server-host:5913`，然后点击连接按钮。

您可以非常方便的将RTTY嵌入到您现有的平台： `https://your-server-host:5913/#/?id=your-id`

自动登录: `https://your-server:5913/#/?id=device-id&username=device-username&password=device-password`

## 传输文件
从本地传输文件到远程设备

    rtty -R

从远程设备传输文件到本地

    rtty -S test.txt

## [远程执行命令](/COMMAND_ZH.md)

# [捐赠](https://gitee.com/zhaojh329/rtty#project-donate-overview)

# 贡献代码
如果您想帮助[rtty](https://github.com/zhaojh329/rtty)变得更好，请参考
[CONTRIBUTING_ZH.md](https://github.com/zhaojh329/rtty/blob/master/CONTRIBUTING_ZH.md)。

# 技术交流
QQ群：153530783

