# Blueprints

### 概览
想所有的优秀webk开发框架一样，Sails致力于减少构建并运行一个功能性APP的代码量及其花费的工时数。
 _Blueprints_ （蓝图）是Sails用来基于你的应用设计快速生成API的[路由](http://sailsjs.org/documentation/concepts/routes)和[动作](http://sailsjs.org/documentation/concepts/controllers#?actions)的工具。
总得来说, [蓝图路由](http://sailsjs.org/documentation/concepts/blueprints/blueprint-routes) 和 [蓝图动作](http://sailsjs.org/documentation/concepts/blueprints/blueprint-actions) 共同构成了 **蓝图API**,驱动了你每次创建的[RESTful JSON API](http://en.wikipedia.org/wiki/Representational_state_transfer)的内在逻辑.

举个例子, 如果你在你的项目中创建了一个`User.js`模型和一个`UserController.js` 控制器文件，那么蓝图可以让你立即可以通过访问`/user/create?name=joe`来创建用户，访问`/user`来看到应用的用户。这些所有的功能你一行代码都不用写。

蓝图是一种创建原型的强有力工具。但在实际生产中，由于他们可以被覆盖、保留、拓展、禁用，他也可以发挥出极大的效用。

