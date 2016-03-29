# myApp/app.js
### 这个文件的作用
这个文件的存在只是用来告诉你在不运行`sails lift`的情况下，怎样启动你的应用。只有在你使用`npm start` (例如 `node app`)启动服务的时候，你才会用到它。在大多数情况下，你忽略它也不会造成任何影响。

```
/**
 * app.js
 *
 * 不用 `sails lift`的情况下，用`app.js` 来启动你的应用.
 * 运行 `node app.js`来启动服务
 * 在没法用Sails命令行的时候，用这个也很方便。
 *
 * 比如:
 *   => `node app.js`
 *   => `forever start app.js`
 *   => `node debug app.js`
 *   => `modulus deploy`
 *   => `heroku scale`
 * 
 *
 * 也支持相同的命令行参数
 * 比如:
 * `node app.js --silent --port=80 --prod`
 */

// 确保 "sails" 可以定位到:
var sails;
try {
	sails = require('sails');
} catch (e) {
	console.error('要用 `node app.js`运行程序, 你要在你的程序所在文件夹安装`sails`');
	console.error('请运行 `npm install sails`');
	console.error('另外, 你以全局方式安装了sails (即你运行过 `npm install -g sails`), 你可以用 `sails lift`.');
	console.error('当你运行 `sails lift`, 如果本地有 `./node_modules/sails` 程序依旧会使用它,');
	console.error('但如果没有, 程序会使用全局的Sails!');
	return;
}

// 试着获取 `rc` 依赖
var rc;
try {
	rc = require('rc');
} catch (e0) {
	try {
		rc = require('sails/node_modules/rc');
	} catch (e1) {
		console.error('找不到依赖包: `rc`.');
		console.error('你的 `.sailsrc` 文件将会被忽略.');
		console.error('要解决这个问题，运行:');
		console.error('npm install rc --save');
		rc = function () { return {}; };
	}
}


// 启动服务
sails.lift(rc('sails'));

```


