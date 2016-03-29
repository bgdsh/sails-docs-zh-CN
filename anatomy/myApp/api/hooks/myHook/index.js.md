# myApp/api/hooks/myHook/index.js
### 用途
这是一个项目 [项目钩子](http://sailsjs.org/documentation/concepts/extending-sails/Hooks/projecthooks.html)的示例，用来给Sails添加功能。
查阅 [钩子](http://sailsjs.org/documentation/concepts/extending-sails/Hooks) 概念章节来了解更多.

```js

module.exports = function(sails) {

  // 这个变量将会是私有的
  // var foo = 'bar';

  // 这个变量是公有的
  // this.abc = 123;

  return {

    // 在这个钩子已经初始化完成之前，暂停Sails启动
    // ready: false,

    // 创建钩子的设置
    defaults:{
    },

    // 在钩子初始化之前做点什么
    configure: function(done){
      return done();
    },

    // 钩子的逻辑
    initialize: function(done){
      // 这个变量可以通过sails.hooks.myhook.numRequestsSeen访问
      this.numRequestsSeen = 0;
      // 这个变量可以通过sails.hooks.myhook.numUnhandledRequestsSeen访问
      this.numUnhandledRequestsSeen = 0;
      return done();
    },

    routes: {
      before: {
        // 这个路由将会先于config/routes.js中的路由匹配
        'GET /*': function (req, res, next) {
           this.numRequestsSeen++;
           return next();
        }
      },
      after: {
        // 这个路由将会滞后于config/routes.js中的路由匹配
        'GET /*': function (req, res, next) {
           this.numUnhandledRequestsSeen++;
           return next();
        }
      }
    }

  };
};
```

<docmeta name="displayName" value="index.js">


