# 开始

## 安装
用命令行安装最新的稳定发布版:

	sudo npm -g install sails

在Windows上 (或者在装了HomeBrew的Mac上), 你不需要sudo:

	npm -g install sails

> 安装Sails的时候，你将会看到一些 `npm WARN deprecated` 消息.  他们可以被忽略，不会有什么安全问题。它们并非来自sails本身，而是sails的依赖库依赖了其它更老的库。Sails团队致力于保证框架安全、稳定，有时（也可能是确实疏忽了），需要用到更老版本的依赖。看 [这篇帖子](https://github.com/balderdashy/sails/issues/3582#issuecomment-185297653) 可以了解到更多关于警告的东西,[这篇](https://github.com/balderdashy/sails/pull/3180) 主要是讲如何更新依赖包。

## 创建一个新的Sails项目
创建一个新的应用:

	sails new testProject

然后将服务器启动:

	cd testProject
	sails lift

然后, 如果你访问(http://localhost:1337/) 可以看到默认主页.
现在，让我们用Sails做一些很酷的事情吧.

