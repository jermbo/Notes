# Gulp Work Flow

Gulp is toolkit for automating painful or time-consuming tasks in your development workflow, so you can stop messing around and build something. [Gulp](http://gulpjs.com/)

## Getting Started

### Terminal Options

PC Users go get [Babun](http://babun.github.io/). Install and pin to task bar. ( I haven't quite figured out where its located by default. ) Mac Users the normal terminal works. But if you want a more feature rich terminal download [iTerm2](https://www.iterm2.com/). 

### Install Node

Go to the [Node website](https://nodejs.org/en/) and download the installer. Open the wizard and follow the bouncing ball. 

Once you have Node and your terminal of choice, open up your terminal and check a few things. You should be able to type `node -v` and the should see something like `v6.9.4`. ( Or what ever version you have installed ) Also, make sure npm is installed, type `npm -v` and you should see `v3.10.10`. ( Or what ever version you have installed. This is typically installed with node. )

### Install Gulp

First thing you want to do is install Gulp globally. You accomplish this by executing this command in the terminal. `npm install -g gulp`

Get used to this command `npm install` this will be used a lot. The `-g` flag is setting this install to the global directory so it can be utilize the CLI ( command line interface ) in every project.

### Navigate to CWD ( Current Working Directory)

The very first thing you need to do is navigate to your working directory that you will be working out of. The easiest way of doing that is, in the terminal type `cd ` and drag your folder into the window. This will give you the path to your folder. To make sure you are in the right directory, in the terminal type `ls -l`. This will list out the folders and files in your current directory. If you see a `package.json` and `gulpfile.js` you are in the right place. 

### Getting Dependencies 

Once you are in the directory with the package.json and gulpfile.js you need to run `npm install`. This will get you all the dependencies required for the project. Depending on the size of the dependency list and your internet connection it could take a couple of minutes to complete. Once done, you will notice a `node_modules` folder in your structure.

## Running Gulp

Now that you have everything for the project installed open your `gulpfile.js` and find out what tasks you have available to you. A good project should have a task list or comments at the top on what to do. In your terminal run the following command 

```powershell
gulp help
```
If this is set up properly you should see something like this

```powershell
Main Tasks
------------------------------------
default
dev
help

Sub Tasks
------------------------------------
dev-bsReload
dev-html
dev-images
etc..
```

## Modifying Gulpfile.js

Until we get project standards in place each project will be slightly different. The current version of the `gulpfile.js` has variables set at the top, so the only thing that should need to be changed are file path sources and destinations. 

*Quick Note : if you see `./` in a path. That is simply stating start from the directory where the file is located* 

### Adding plugins

When there is something you want to automate, do a google search for 'thing i want to do gulp'. There is a task runner for just about everything now-a-days. You can also search the [Gulp plugin repository](http://gulpjs.com/plugins/). Though, I prefer the google route because it usually comes with sample code. 

Let's say you want to uglify your JavaScript files, search 'uglify js gulp'. The first link that comes up is [gulp-uglify](https://www.npmjs.com/package/gulp-uglify). This is where you will, usually, see the documentation and usage examples.

To add a plugin to your project you need to install it and save it to your package.json file. You can do that by opening the terminal, in your project folder where the package.json lives, and type the following command : 

```javascript
npm install --save-dev gulp-uglify 
```

Once the plugin has been loaded into the node_modules, you need to add to the gulp file. Normally speaking you add a new plugin as follows

```javascript
const uglify = requre('gulp-uglify');
```

Then you use it where you need it. But, you might have a lot of plugins in your system so doing this for each plugin can get tedious and very long. Luckily there is a plugin to solve this problem. It's called [Gulp Load Plugins](https://www.npmjs.com/package/gulp-load-plugins). This is already being utilized in our system and it looks like 

```javascript
const $ = require('gulp-load-plugins')({ lazy: true });
```

This sets all the plugins to the $ variable and you access every plugin though it. In your task, when you want to use the uglify plugin you would :

```javascript
.pipe( $.uglify() )
```

Two things to note about using this plugin. First, the 'gulp-' from the folder name can be dropped as it is assumed. Second, if your plugin name has dashes in it, they are converted to camel case. For example `gulp-long-pulgin-name` will be utilized as `$.longPluginName` when you want to reference it.

## Gulp API

This deserves its onw file as we can get into a lot of details about this topic. Here is an attempt to give you the information you need to know about the [Gulp API](https://github.com/gulpjs/gulp/blob/master/docs/API.md)

You have 5 methods at your disposal, `.task() | .src() | .dest() | .watch() | .pipe()`

### .task()

Tasks are what you use to define blocks of items you want to run. The method takes 3 parameters. Task Name, Array of Tasks, Callback Function. The only one required is the Task name. Example usage looks like :

```javascript
gulp.task('styles', () => { 
  // do stuff
});
```

This can be run by executing the command `gulp styles` in the terminal that is in the correct working directory. 

If you wanted tasks to be run before starting the block of code in styles, you pass in an array of task names. Example usage looks like : 

```javascript
gulp.task('styles', ['otherTask1', 'otherTask2'], () => {
  // do stuff
});
```

You could also have one gulp task that only triggers other tasks. For example, in your dev set up you want to run multiple tasks - styles, html, images, scripts, watch. That is a lot to type to get your dev environment up. You could create a task to kick things off, looks like this :

```javascript
gulp.task('startDev', ['styles', 'html', 'images', 'scripts', 'watch']);
```

### .src()

Emits files matching provided glob or an array of globs. Returns a stream of files that can be piped to plugins. In our examples, we have it the config variable declared at the top. Example usage looks like : 

```javascript
gulp.src(config.styles.source + '/site.less')
```

### .dest()

Can be piped to and it will write files. Re-emits all data passed to it so you can pipe to multiple folders. Folders that don't exist will be created. Example usage looks like :

```javascript
gulp.src(config.styles.source + '/site.less')
  .pipe($.less())
  .pipe(gulp.dest(config.styles.build))
```

### .watch()

Watch files and do something when a file changes. This always returns an EventEmitter that emits `change` events.

```javascript
gulp.watch(config.styles.source + '/**/*.less', ['styles']);
```