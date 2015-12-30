# Getting started with Grunt

by [JuanMa Garrido](#trainer)

<!-- ######################## COVER ######################## --> 

!SLIDE #Cover

![Grunt Logo](img/grunt-logo.png)

## Getting started with GRUNT

<!-- ######################## TEACHER ######################## --> 

!SLIDE #trainer no-bullet-list

## Teacher: JuanMa Garrido
 
<ul>
<li><a class="icon-envelope" href="mailto:JuanMa.Garrido@gmail.com" target="_blank">JuanMa.Garrido@gmail.com</a></li>
<li><a class="icon-twitter" href="https://twitter.com/juanmaguitar" target="_blank">@juanmaguitar</a></li>
<li><a class="icon-linkedin" href="http://www.linkedin.com/in/juanmagarrido" target="_blank">http://www.linkedin.com/in/juanmagarrido</a></li>
<li><a class="icon-github" href="https://github.com/juanmaguitar" target="_blank">https://github.com/juanmaguitar</a></li>
</ul>

<!-- ######################## CONTENTS ######################## --> 

!SLIDE #contents

## Contents

1. What is Grunt?
1. <span class="icon-keyboard"></span> Using Grunt in an existing project


<!-- ######################## WHAT IS GRUNT ######################## --> 

!SLIDE what

> Grunt is a @@Task Runner@@ 

!SLIDE what2

[Originally described](http://bocoup.com/weblog/introducing-grunt/) as:

> Grunt is a @@task-based@@ @@command line@@ @@build tool@@ for @@JavaScript@@ projects.

<!-- ######################## CLEAR IDEAS ######################## --> 

!SLIDE clear-ideas small no-bullet-list

## Clear Ideas about Grunt

- ?<span class="icon-building"></span>Grunt and Grunt-plugins are installed and managed via [npm](https://npmjs.org/), the [Node.js](http://nodejs.org/) package manager.
- ?<span class="icon-terminal"></span>To use _Grunt from comand line_ we have to install (globally) the [Grunt's CLI](http://gruntjs.com/using-the-cli) → `npm install -g grunt-cli`
- ?<span class="icon-terminal"></span>In _new projects_ we install Grunt and Grunt-plugins as node modules → `npm install --save-dev grunt grunt-contrib-jshint`
- ?<span class="icon-terminal"></span>In _existing Grunt projects_ we install Grunt and Grunt-plugins with → `npm install`

!SLIDE clear-ideas no-bullet-list

## Clear Ideas about Grunt

<!-- 
- ?<span class="icon-cogs"></span>The _grunt command line_ (globally) runs the grunt 'package' at `node_modules` (locally)
-->

- Main Files:
	- ?<span class="icon-file"></span>`@@@package.json@@@`: The Grunt runner and Grunt plugins used in the _Gruntfile.js_ are set as project dependencies in this file
	- ?<span class="icon-file"></span>`@@@Gruntfile.js@@@`: The tasks are defined/configured and grunt plugins are loaded in this file 
	
!SLIDE clear-ideas no-bullet-list smallcode

## Clear Ideas about Grunt

- <span class="icon-code"></span> [sample](http://browsenpm.org/package.json) [`package.json`](https://docs.npmjs.com/files/package.json):

```
{
  "name": "my-project-name",
  "version": "0.1.0",
  "@@devDependencies@@": {
    "grunt": "~0.4.5",
    "grunt-contrib-jshint": "~0.10.0",
    "grunt-contrib-nodeunit": "~0.4.1",
    "grunt-contrib-uglify": "~0.5.0"
  }
}
```

!SLIDE clear-ideas no-bullet-list smallcode smaller

## Clear Ideas about Grunt

- <span class="icon-code"></span> [sample](http://gruntjs.com/sample-gruntfile) `Gruntfile.js`:

```
module.exports = function(grunt) {
  grunt.@@initConfig@@({
    jshint: {
      files: ['Gruntfile.js', 'src/**/*.js', 'test/**/*.js'],
      options: {
        globals: {
          jQuery: true
        }
      }
    },
    watch: {
      files: ['<%= jshint.files %>'],
      tasks: ['jshint']
    }
  });
  grunt.@@loadNpmTasks@@('grunt-contrib-jshint');
  grunt.loadNpmTasks('grunt-contrib-watch');
  grunt.@@registerTask@@('default', ['jshint']);
};
```

<!-- ######################## USING GRUNT ######################## --> 

!SLIDE smallcode no-bullet-list

## <span class="icon-keyboard"></span> Using Grunt in an existing project

- @@Steps@@:

	1. Change to the project's root directory.
	1. Install project dependencies with `npm install`
	1. Run Grunt with `grunt`

!SLIDE smallcode

## <span class="icon-keyboard"></span> Using Grunt in an existing project

```
$ git --version
$ node -v
$ npm -v
$ npm install -g grunt-cli
$ git clone https://github.com/juanmaguitar/grunt-workshop.git
$ cd grunt-workshop
$ npm install
$ grunt --version
$ grunt -h
$ grunt tasks
$ grunt compass
$ grunt shower
$ grunt serve

```

<!-- ######################## MORE INFO ######################## --> 

!SLIDE

##More info

- [Grunt | Official Site](http://gruntjs.com/)
- [Introducing Grunt | Boucup](http://bocoup.com/weblog/introducing-grunt/)
- [Get Up And Running With Grunt | Smashing Magazine](http://www.smashingmagazine.com/2013/10/29/get-up-running-grunt/)
- [Meet Grunt: The Build Tool for JavaScript | tutsplus](http://code.tutsplus.com/tutorials/meet-grunt-the-build-tool-for-javascript--net-24856)
- [JS Task Runners Comparison: Grunt vs Cake vs Gulp vs Broccoli](http://blog.cozycloud.cc/technic/2014/06/18/task-runners-comparison/)

