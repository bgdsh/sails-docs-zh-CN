# Sails是啥?


Sails当然是一种web开发框架，但退一步讲，这意味着什么？ 有时候，当我们提到『Web』,我们说的是前端网页。我们会想到一些概念，诸如网页标准、HTML5、CSS3；也会想到一些框架，诸如Backbone, 或 Angular,或 jQuery。Sails不是前面说的这种Web开发框架。Sails可以很好地和这些框架配合使用，但是并不能 _替代_ 这些库。
除此之外，当我们提到『web开发框架』的时候，我们是指『网站后端』。这会使我们想到诸如REST、HTTP、WebSockets等词汇或者是Java、Ruby或Node.js等技术。网站后端框架可以帮助你来做诸如构建API、提供HTML文件、处理成千上万的并发用户。Sails就是这种框架。
## 约定大于配置

Sails可以完成许多和其它MVC框架一样的目标，用到了许多相同的方法论。这是有意为之的。一以贯之的方法可以促使每个参与应用开发的人更加可预期、高效。
假如在一家公司开始用Sails开发一个应用（如果你愿意，也可以是你自己的公司）。如果你的团队成员以前用过诸如Zend, Laravel, CodeIgniter, Cake, Grails, Django, ASP.NET MVC, or Rails, Sails这些框架，会感到非常熟悉。不仅限于此，他们可以查看一个Sails项目，可以大概知道怎样编写基本的模式，这些模式他们可能过去已经一遍一遍地写过了，不管他们以前是会PHP, Ruby, Java, C#, or Node.js。那如果说这是你第二次、第三次构建Sails应用呢？从一个你亲切、熟悉的模板开始可以让你的开发更高效。在许多情况下，你甚至可以复用一些你的后端代码。

> **历史回溯**
>
> 并非Sails发明了这个概念--  [其实已经很多年了](https://en.wikipedia.org/wiki/Convention_over_configuration)。 设置早于Ruby On Rails将这个概念普及的时候，这也是JavaBean的核心信条。是对于上世纪90年代末本世纪初传统的Java网站开发框架中非常详细的XML配置的强力阻击。


## 松散耦合

一种尺度处处适用的开发方法已经过时了。我们需要一种工具，可以帮助我们遴选出一些组件（组合起来）以满足我们的需求。这其实是一种相对于其他方式来说的『懒办法』。Sails的方法是将组件解耦，这样一来你就可以任意地将组件添加到项目或者移除掉。
Node在其核心创造了一种『够用』（实验并使作品运转起来）文化。Sails拥护这种态度，并努力为你提供随时可能会用到的工具。你对于Sails自动化水品的期望与你可以花多少时间在项目上和你的Node开发经验有直接关联。当你有充足的时间时，Sails足够灵活可以让你探索并创造。当你没时间时，他可以提供默认既有的自动化工具。
Sails采用『拙朴』的require来完成解耦。没有『魔法』或者是时间用来构建某些组件：是整体的一部分但不必为了整体可以运转而按顺序实现。 举个例子，控制器、数据模型、配置文件就是Node模块。Sails采用某种约定来帮忙。Sails在Controllers文件夹中找到名叫UserController.js的文件，它就推断这个文件确实是用户模块的控制器。另外一个例子是policies。policies允许你在所有或者一部分控制器里运行一小段代码。最酷的地方是链接policy和控制器/操作的配置文件是分开的。这就意味着你可以写一大串不同的policies，他们在不同的Sails应用中都是可用的。你可以稍后决定在哪个控制器/动作上应用它们。

Sails核心包含20种不同的钩子：修改服务器运行环境的模块、添加中间件、绑定路由监听、或者给框架附加更多的能力。它给你了重写或禁用Sails的每个组件和配置参数的能力。当Sails启动的时候，这些钩子就加载了。你甚至能为特定的钩子进行单独配置。这是钩子和服务的主要区别之一。

另外一个松耦合的例子是配置文件。 你的项目是否需要一些配置项？没问题，在config文件夹创建一个文件，采用常用的module.exports模式。这个模块的所有东西都会在Sails的全局对象处可见。
几乎所有的Sails组件都可以被忽略、复写或者拓展。比如，Sails有一组叫做蓝图的工具。这些蓝图工具把关于路由和CURD相关的操作搞得非常简单。但假如你想采用读取、更新、删除操作，但是创建操作需要做一些别的操作。没问题，就只创建一个创建操作，其它CURD操作也会继续运转。你的定制化操作将从属于蓝图操作。就是这么简单。

> 链接:
> + [Unix哲学](http://blog.izs.me/post/48281998870/unix-philosophy-and-node-js)
> + [Node文化](https://blog.nodejitsu.com/the-nodejs-philosophy/)

## MVC 架构
Sails implements the aforementioned Model, View, Controller (MVC) architecture for Node.js. You can learn more about MVC <a href="https://docs.djangoproject.com/en/dev/faq/general/#django-appears-to-be-a-mvc-framework-but-you-call-the-controller-the-view-and-the-view-the-template-how-come-you-don-t-use-the-standard-names">here</a>, <a href="http://symfony.com/legacy/doc/askeet/1_0/en/3">here</a>, and <a href="http://guides.rubyonrails.org/getting_started.html#the-mvc-architecture">here</a>, but the tl;dr is that it's the really awesome, industry-standard way of doing things for modern web apps.
If you're wondering if Sails is a "proper MVC", you're probably right! It wasn’t made to mimic Django, Zend, or Rails; it was made to resemble the MVC architecture we’re used to while still unlocking the features necessary to leverage the unique advantages of Node.js: seamless WebSockets support, advanced memory management using streams, and composable, data-driven APIs using the powerful concept of chainable middleware from Connect/Express.

## 现代风味
Sails does a few things other MVC frameworks can't do:


### Socket.io / Realtime / WebSockets
Sails supports transport agnostic routing, which allows your controllers/policies to automatically handle Socket.io / WebSocket messages.  In the past, you'd have to maintain a separate code base to make that happen. This makes it much easier to add pubsub features, in particular the server-originated or 'comet' notifications you need for realtime apps, realtime analytics dashboards, and multiplayer games.

### 性能
Node has fantastic performance. Specifically, we've had some great results using 4 EC2 small servers to scale Sails to 10,000 concurrent connections.  In that case, the bottleneck was actually our test client.  Sails users have reported getting about 9k concurrent connections on one EC2 medium server.

+ Built-in support for Redis session store, and Redis MQ for reverse pubsub routing

### Node.js
Node.js is the fastest-growing, all-javascript solution to <a href="https://www.youtube.com/watch?v=jo_B4LTHi3I">server-side development</a>. Writing your code in one language on the front-end and back-end means less context-shifting, faster development, and better apps.

### Express
Sails's controllers and policies are really just [Express](https://github.com/expressjs/) middleware. This means your Sails app logic is interoperable with existing Express apps, and vice versa

+ Supports the existing ecosystem of Express middleware

### REST 蓝图
  + Automatically generated JSON API for manipulating models (You don't have to write any backend code to build simple CRUD apps)
  + Automatic route bindings for your controller actions

###  以下controller/action层级的中间件内置支持:
  + Authentication logic
  + Role-based access control
  + Custom policies (e.g. file storage quotas)


## 会给前端工程师带来便利的特性
If you are developing an HTML/CSS front-end powered by Sails, there are some other convenience features we've included that might help you out.

### 对Grunt的支持
As of Sails v0.9, all new projects come with a Gruntfile. Grunt is to Node.js as mvn/ant is to Java, or as rake is to Ruby. It has a strong, supportive community, and a wide array of plugins and build tools. Adding support for your favorite template engine or css/js preprocessor is as easy as modifying your project's Gruntfile

### Asset bundling
Sails bundles support for LESS and JST templates

  + If you use the `--linker` option when creating your new project, your assets will be automatically bundled up and included in your layout HTML
  + Front-end support for SASS, Handlebars, CoffeeScript, Stylus, TypeScript, etc. is as easy as modifying your app's Gruntfile
  + In production mode, Sails will also minify and concatenate your assets
  + If you need to take web performance even further (this comes up for mobile web apps in particular), you can run `sails build` to output a CDN-ready snapshot of your apps assets

### PhoneGap、Chrome拓展、对单页应用友好
  + `sails build` spits out a ready-to-deploy `www` directory for use in all of the sorts of places where you need indepenedent, API-driven front-end code
  + Sails has easy-to-use CORS integration
  + Built-in support for cross-site request forgery (CSRF) protection, with a handy token-based option for single-page apps



## Finally, a note for UX-focused guys/gals
> ####一个极客如是说:

> 我和我的团队在<a href="http://balderdash.co">Balderdash</a>的web和移动APP上做了很多工作。不像以往，你的应用不光要能工作，而且要看起来高大上。
> 我最开始构建Sails的目的是为我们的初创公司和企业客户解决API驱动的重客户端的项目。这样一来，顶级佳作成了业界标准，尤其是用了BackBone、Angular、Ember、Knockout等之后。减少了在app后端编码上花的时间和精力，就可以让你有更多地时间关注如何让你的app更炫酷。你的后端代码越容易编写与维护,你就越敏捷。你越敏捷，你的项目就越能满足用户的需求，你就能更快地修复bug，你就更能适应....我觉得你应该明白我的意思了。

