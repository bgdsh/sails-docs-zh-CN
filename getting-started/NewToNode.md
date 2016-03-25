# [Node.js](https://soundcloud.com/marak/marak-the-node-js-rap)新手？
没问题的，我们将给你指引正确的方向。
[nodejs.org](http://nodejs.org)上对Node.js的介绍:
> Node.js是一个构建于 Chrome的JavaScript运行环境之上的，用于快速构建可拓展的网络应用的平台。Node.js使用事件驱动、非阻塞I/O模型，以确保其轻量、高效。非常适合于构建运行在分布式设备上的数据密集型的实时应用。

更简单地说，Node.js允许我们在浏览器环境之外快速高效地运行JavaScript代码。让在前后端使用相同的编程语言成为了可能。
## 我需要什么操作系统？

Node.js可以安装在大多数主流的操作系统之上。MacOSX,主流的Linux操作系统，Windows系统，都是支持的。

现在, 看看你有下面列的哪种系统，选择并在上面安装node.js:

我有 [Mac OSX](http://sailsjs.org/get-started#?install-on-osx)

我有 [Linux](http://sailsjs.org/get-started#?install-on-linux)

我有 [Windows](http://sailsjs.org/get-started#?install-on-windows)

<h2>
<a id="install-on-osx" name="/getStarted?q=--install-on-osx-" class="anchor" href="http://sailsjs.org/getStarted?q=--install-on-osx-"><span class="mini-icon mini-icon-link"></span></a>
在OSX上安装
</h2>

使用 [安装包](http://nodejs.org/download/):

直接 [下载Mac版安装包](http://nodejs.org/download/)

使用 [homebrew](https://github.com/mxcl/homebrew):

    brew install node

使用 [macports](http://www.macports.org/):

    port install nodejs

<h2>
<a id="install-on-linux" name="/getStarted?q=--install-on-linux-" class="anchor" href="http://sailsjs.org/getStarted?--install-on-linux-"><span class="mini-icon mini-icon-link"></span></a>
在Linux上安装
</h2>

### Ubuntu, Mint

安装方法:

    sudo apt-get install python-software-properties python g++ make
    curl -sL https://deb.nodesource.com/setup_4.x | sudo -E bash -
    sudo apt-get install -y nodejs

上述命令在稳定版的Ubuntu上安装稳定版的Node.js。 Quantal (12.10) 用户可能需要安装 *software-properties-common* 的依赖包来使 `add-apt-repository` 命令起作用: `sudo apt-get install software-properties-common`

有一个安装包和Node名字冲突了 (Amateur Packet Radio Node Program), node字节码文件已经从 `node` 改名为 `nodejs`. 你需要把 `/usr/bin/node` 链接到 `/usr/bin/nodejs` 或者 你可以卸载 the Amateur Packet Radio Node Program 以避免冲突.

### Fedora

[Node.js](https://apps.fedoraproject.org/packages/nodejs) and [npm](https://apps.fedoraproject.org/packages/npm) are available in Fedora 18 and later.  Just use your favorite graphical package manager or run this on a terminal to install both npm and node:

    sudo yum install npm

### RHEL/CentOS/Scientific Linux 6

Node.js and npm are available from the [Fedora Extra Packages for Enterprise Linux (EPEL)](https://fedoraproject.org/wiki/EPEL) _testing_ repository.  If you haven't already done so, first [enable EPEL](https://fedoraproject.org/wiki/EPEL#How_can_I_use_these_extra_packages.3F) and then run the following command to install node and npm:

    su -c 'yum --enablerepo=epel-testing install npm'

### Arch Linux
Node.js is available in the Community Repository.

    pacman -S nodejs

### Gentoo
Node.js is available in official gentoo portage tree. You have to unmask it.

    # emerge -aqv --autounmask-write nodejs
    # etc-update
    # emerge -aqv nodejs

### Debian, LMDE

For *Debian sid (unstable)*, [Node.js is available in the official repo](http://packages.debian.org/search?searchon=names&keywords=nodejs).

For *Debian Wheezy (stable)*, [Node.js is available in wheezy-backports](http://packages.debian.org/wheezy-backports/nodejs). To install [backports](http://backports.debian.org/Instructions/), add this to your sources.list (`/etc/apt/sources.list`):

    deb http://YOURMIRROR.debian.org/debian wheezy-backports main

Then run:

    apt-get update
    apt-get install nodejs

For *Debian Squeeze (oldstable)*, your best bet is to compile node by yourself (as `root`):

    apt-get install python g++ make
    mkdir ~/nodejs && cd $_
    wget -N http://nodejs.org/dist/node-latest.tar.gz
    tar xzvf node-latest.tar.gz && cd `ls -rd node-v*`
    ./configure
    make install

### openSUSE & SLE
[Node.js stable repos list](https://build.opensuse.org/package/show?package=nodejs&project=devel%3Alanguages%3Anodejs). Also node.js is available in openSUSE:Factory repository.

Available RPM packages for: openSUSE 11.4, 12.1, Factory and Tumbleweed; SLE 11 (with SP1 and SP2 variations).

Example install on openSUSE 12.1:

    sudo zypper ar http://download.opensuse.org/repositories/devel:/languages:/nodejs/openSUSE_12.1/ NodeJSBuildService
    sudo zypper in nodejs nodejs-devel

### FreeBSD and OpenBSD
Node.js is available through the ports system.

    /usr/ports/www/node

Development versions are also available using ports

    cd /usr/ports/www/node-devel/ && make install clean

or packages on FreeBSD

    pkg_add -r node-devel

The Node Package Manager is not installed along with Node.js by default on FreeBSD and will be needed for development and installing dependencies.

    /usr/ports/www/npm

Also note that FreeBSD 10 using clang will conflict with the occasional build scrpt (which assumes gcc) using node-gyp, and can be resolved by setting an envvar.

    CXX=c++

<h2>
<a id="install-on-windows" name="/getStarted?q=--install-on-windows-" class="anchor" href="http://sailsjs.org/getStarted?q=--install-on-windows-"><span class="mini-icon mini-icon-link"></span></a>
Install on Windows
</h2>

Using [a package](http://nodejs.org/download/):

_Simply [download Windows Installer](http://nodejs.org/download/)._

Using [chocolatey](http://chocolatey.org) to install [Node](http://chocolatey.org/packages/nodejs):

    cinst nodejs

or for [full install with NPM](http://chocolatey.org/packages/nodejs.install):

    cinst nodejs.install


## On to Sails.js!
Once Node.js is installed on your system, you can go ahead and [install Sails](http://sailsjs.org/get-started#?getting-started-installation).

## Further help!
We know that sometimes things don't go as planned. If you still have any issue with this, please feel free to visit Node.js's [IRC Channel](irc://irc.freenode.net/node.js) or our own [IRC Channel](irc://irc.freenode.net/sailsjs).

