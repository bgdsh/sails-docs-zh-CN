# myApp/Gruntfile.js
### Purpose

Sails uses [Grunt](http://gruntjs.com) for asset management. This file contains the entry point for the default asset pipeline in Sails; that is, the code that does stuff like compiling LESS stylesheets, minifying scripts for production, and precompiling and injecting client-side templates.

Sails' integration with Grunt is fully customizable, but for most use cases, this file (`Gruntfile.js`) should remain unchanged.  Instead, install Grunt plugins or add your own custom logic as individual files in the [`tasks/`](./tasks) folder.

To learn more about working with static assets in Sails, check out the [conceptual documentation on assets](http://sailsjs.org/documentation/concepts/assets).  For a broader introduction to Grunt tasks in general, see [Grunt's docs on configuring tasks](http://gruntjs.com/configuring-tasks).


<docmeta name="displayName" value="Gruntfile.js">

<div www-sjs-anatomy-boilerplate>

```javascript
/**
 * Gruntfile
 *
 * This Node script is executed when you run `grunt` or `sails lift`.
 * Its purpose is to load the Grunt tasks in your project's `tasks`
 * folder, and allow you to add and remove tasks as you see fit.
 * For more information on how this works, check out the `README.md`
 * file that was generated in your `tasks` folder.
 *
 * WARNING:
 * Unless you know what you're doing, you shouldn't change this file.
 * Check out the `tasks` directory instead.
 */

module.exports = function(grunt) {


	// Load the include-all library in order to require all of our grunt
	// configurations and task registrations dynamically.
	var includeAll;
	try {
		includeAll = require('include-all');
	} catch (e0) {
		try {
			includeAll = require('sails/node_modules/include-all');
		}
		catch(e1) {
			console.error('Could not find `include-all` module.');
			console.error('Skipping grunt tasks...');
			console.error('To fix this, please run:');
			console.error('npm install include-all --save`');
			console.error();

			grunt.registerTask('default', []);
			return;
		}
	}


	/**
	 * Loads Grunt configuration modules from the specified
	 * relative path. These modules should export a function
	 * that, when run, should either load/configure or register
	 * a Grunt task.
	 */
	function loadTasks(relPath) {
		return includeAll({
			dirname: require('path').resolve(__dirname, relPath),
			filter: /(.+)\.js$/
		}) || {};
	}

	/**
	 * Invokes the function from a Grunt configuration module with
	 * a single argument - the `grunt` object.
	 */
	function invokeConfigFn(tasks) {
		for (var taskName in tasks) {
			if (tasks.hasOwnProperty(taskName)) {
				tasks[taskName](grunt);
			}
		}
	}




	// Load task functions
	var taskConfigurations = loadTasks('./tasks/config'),
		registerDefinitions = loadTasks('./tasks/register');

	// (ensure that a default task exists)
	if (!registerDefinitions.default) {
		registerDefinitions.default = function (grunt) { grunt.registerTask('default', []); };
	}

	// Run task functions to configure Grunt.
	invokeConfigFn(taskConfigurations);
	invokeConfigFn(registerDefinitions);

};

```
