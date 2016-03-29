![Squiddy reads the docs](http://sailsjs.org/images/squidford_swimming.png)

# Sails.js 文档
译者注：我连文件夹都翻译了，不知道今后还能不能合并。联系我请给我写信：bgd_sh@hotmail.com，坐标魔都。
Sails的稳定发行版的官方文档在这里 [主分支](github.com/balderdashy/sails-docs)。[Sails官方网站](http://sailsjs.org) 的大部分内容是从此处编译的。

## 文档的其它语言版本

Sails的文档已经被翻译为几种不同的语言。下面的列表是我（主分支的维护者）知道的翻译版本的列表：

| 语言                    | [IETF语言标签](https://en.wikipedia.org/wiki/IETF_language_tag)  | 维护者        | git库                               |
| ---------------------------- | ------- | ------------------ | ---------------------------------- |
| 日语                     | `ja`    | [@kory-yhg](https://github.com/kory-yhg)      | [sails-docs-ja](https://github.com/balderdashy/sails-docs/tree/ja) <br/>(_live on [sailsjs.jp](http://sailsjs.jp)_)
| 西班牙语                      | `es`    | [@eduartua](https://github.com/eduartua/) & [@alejandronanez](https://github.com/alejandronanez)   | [sails-docs-es](https://github.com/eduartua/sails-docs-es)
| 葡萄牙语（巴西）         | `pt-BR` | [@marceloboeira](https://github.com/marceloboeira) & [@gabrielalmir10](https://github.com/gabrielalmir10)   | [sails-docs-pt-BR](https://github.com/balderdashy/sails-docs/tree/pt-BR)
| 繁体中文（宝岛台湾）         | `zh-TW` | [@CalvertYang](https://github.com/CalvertYang)   | [sails-docs-zh-TW](https://github.com/balderdashy/sails-docs/tree/zh-TW)
| 韩语                       | `ko`    | [@sapsaldog](https://github.com/sapsaldog)   | [sails-docs-ko](https://github.com/balderdashy/sails-docs/tree/ko)

> 我们现在用分支来维护不同版本的Sails文档，但维护多语言版本，我们不用这种方式。当你开始一个新的翻译项目之前，我们建议你先读一读[下面更新的内容](#how-can-i-help-translate-the-documentation)-- 流程已经有了一些变化.



## 给Sails文档做贡献

我们欢迎你的帮助!  请给**master**提交PR 包括更正和增量内容在内，这些内容将会被尽快检查、合并。
其次，我们对关于文档维护、社区运作方面的建议持开放态度。请给Google小组写信或者直接在twitter上联系@fancydoilies, @rudeboot, 或 @mikermcneil.

#### 我应该编辑哪个分支?
这取决于你做哪种形式的编辑。一般来说，你可以编辑最新稳定版本的Sails文档（比如[NPM](npmjs.org/package/sails)上的版本），那你编辑这个repo的`master`分支就行了。
但是，如果你正在编辑有关未发布特性的未来版本，这些特性可能还处于建议阶段、对Sails开启了PR或者是一个相关的项目，那你可能想编辑next分支。通常来说叫做「edge」。


| 分支 (在 `sails-docs`)                    | 此版本的Sails文档                                   | 在何处预览     |
|-------------------------------------------------------------------------------------|------------------------|:-------------------|
| [`主分支`](https://github.com/balderdashy/sails-docs/tree/master) | [![NPM version](https://badge.fury.io/js/sails.png)](http://badge.fury.io/js/sails) | [preview.sailsjs.org](http://preview.sailsjs.org)
| [`1.0`](https://github.com/balderdashy/sails-docs/tree/1.0) | 将要到来的 v1.0 发布 _(这个分支还不能访问)_           | [next.sailsjs.org](http://next.sailsjs.org)
| [`0.11`](https://github.com/balderdashy/sails-docs/tree/0.11) | Sails v0.11.x           | [0.11.sailsjs.org](http://0.11.sailsjs.org)


#### 这些文档是怎样编译并推送到网站的?

我们采用一个叫做`doc-templater`的模块来将.md文件转换为网站所需的html文件。从它的库[doc-templater库](https://github.com/uncletammy/doc-templater).你可以了解到更多它的运行原理。
每个.md文件在网站上都有它自己的网页（比如：所有的参考、概念、案例剖析文件），它们必须包含一个特殊的`<docmeta name="displayName">`标签，这个标签有一个`value`属性来指定页面的标题。这将影响文档页面在搜索引擎结果中如何显示，也将会用于在sailsjs.org上导航菜单的显示。
举例:

```markdown
<docmeta name="displayName" value="Building Custom Homemade Puddings">
```

#### 我的修改将何时呈现在网站上?

当文档的变化合并到了特定的分支（版本号与当前Sails稳定版相同），翻译的文档就会呈现给大家。我们不能合并直接发布到这个分支（主分支）的pr，主文档的主要目的是映射当前sailsjs.org网站上呈现的内容。你翻译的内容将在下次合并的时候才能呈现。

如果你想看到文档变化看起来是怎样的，你可以访问。一旦文档变化合并到主分支，预览网站就会自动更新。

#### 我能为文档翻译帮上什么忙?
如果你说英语之外的某种语言并且你自愿翻译Sails文档，这是非常棒的。如果你想为上表所列的已有文档做贡献，用那个分支上所留的说明联系文档的维护者即可。
如果你的语言未出现在上面的表中，你想从头开始一个翻译项目，按照如下步骤进行：

+ Fork 这个库 (`balderdashy/sails-docs`) 并将你的分支改名为 `sails-docs-{{IETF}}` 其中 {{IETF}} 是指 [IETF 语言标签](https://en.wikipedia.org/wiki/IETF_language_tag) 中代表你的语言的标签.
+ 修改README文件来总结你目前的进展。提供你认为对其他人来阅读你的文档有帮助的信息，让有兴趣的翻译者知道怎么联系你。
+ 发一个pr,修改上面的表，增加一个你的分支的链接。
+ 如果你的对你的第一个完成版满意的话，发一个issue，我们的文档团队非常乐意帮你在Sails网站上进行预览展示。将文档部署在一个域名（你的或者是sailsjs.org的子域名，任何一个都非常有意义）下，和其它Sails社区的人一起分享它。


#### 我还能帮上什么别的忙?

关于给Sails做贡献，更多的内容请参详[Contribution Guide](https://github.com/balderdashy/sails/blob/master/CONTRIBUTING.md).


