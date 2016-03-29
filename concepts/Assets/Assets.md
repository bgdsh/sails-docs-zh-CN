# Assets

### 概览
Assets是指存放在服务器上，可以允许外界访问的[静态文件](http://en.wikipedia.org/wiki/Static_web_page)(js, css, images, 等)。在Sails中，这些文件被存放在[`assets/`](http://sailsjs.org/documentation/anatomy/myApp/assets) 文件夹，当你启动程序的时候他们将被从这里处理并同步到隐藏的临时文件夹`.tmp/public/`中。这个`.tmp/public`文件夹的内容才是真正的Sails提供给外界的。大致上和[express](https://github.com/expressjs)的"public"或者Apache这种web服务器的"www"文件夹类似。这个中间步骤可以让Sails准备/预编译静态资源，以备客户端使用。这些资源包括LESS、ConffeeScript、SASS、雪碧图、Jade模板等等。

### Static middleware

Behind the scenes, Sails uses the [static middleware](http://www.senchalabs.org/connect/static.html) from Express to serve your assets. You can configure this middleware (e.g. cache settings) in [`/config/http.js`](http://sailsjs.org/documentation/reference/sails.config/sails.config.http.html).

##### `index.html`
Like most web servers, Sails honors the `index.html` convention.  For instance, if you create `assets/foo.html` in a new Sails project, it will be accessible at `http://localhost:1337/foo.html`.  But if you create `assets/foo/index.html`, it will be available at both `http://localhost:1337/foo/index.html` and `http://localhost:1337/foo`.

##### Precedence
It is important to note that the static [middleware](http://stephensugden.com/middleware_guide/) is installed **after** the Sails router.  So if you define a [custom route](http://sailsjs.org/documentation/concepts/Routes?q=custom-routes), but also have a file in your assets directory with a conflicting path, the custom route will intercept the request before it reaches the static middleware. For example, if you create `assets/index.html`, with no routes defined in your [`config/routes.js`](http://sailsjs.org/documentation/reference/sails.config/sails.config.routes.html) file, it will be served as your home page.  But if you define a custom route, `'/': 'FooController.bar'`, that route will take precedence.



<docmeta name="displayName" value="Assets">


