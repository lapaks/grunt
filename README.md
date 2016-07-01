# grunt

Installing the CLI

Install Grunt's command line interface (CLI) globally. 
You may need to use sudo (for OSX, *nix, BSD etc) or run your command shell as Administrator (for Windows) to do this.

npm install -g grunt-cli

Preparing a new Grunt project
A typical setup will involve adding two files to your project: package.json and the Gruntfile.

package.json: This file is used by npm to store metadata for projects published as npm modules. You will list grunt and the Grunt plugins your project needs as devDependencies in this file.

Gruntfile: This file is named Gruntfile.js or Gruntfile.coffee and is used to configure or define tasks and load Grunt plugins. When this documentation mentions a Gruntfile it is talking about a file, which is either a Gruntfile.js or a Gruntfile.coffee.

package.json
============
{
  "name": "my-project-name",
  "version": "0.1.0",
  "devDependencies": {
    "grunt": "~0.4.5",
    "grunt-contrib-jshint": "~0.10.0",
    "grunt-contrib-nodeunit": "~0.4.1",
    "grunt-contrib-uglify": "~0.5.0"
  }
}

Gruntfile
===========
module.exports = function(grunt) {

  // Project configuration.
  grunt.initConfig({
    pkg: grunt.file.readJSON('package.json'),
    uglify: {
      options: {
        banner: '/*! <%= pkg.name %> <%= grunt.template.today("yyyy-mm-dd") %> */\n'
      },
      build: {
        src: 'src/<%= pkg.name %>.js',
        dest: 'build/<%= pkg.name %>.min.js'
      }
    }
  });

  // Load the plugin that provides the "uglify" task.
  grunt.loadNpmTasks('grunt-contrib-uglify');

  // Default task(s).
  grunt.registerTask('default', ['uglify']);

};

INSTALL GRUNT
npm install grunt --save-dev

<b>USEFUL LINKS</b><br>
GRUNT<br>
http://gruntjs.com/getting-started#installing-the-cli<br>
https://www.youtube.com/watch?v=Pog9WzzXUO0&index=9&list=PLpP9FLMkNf55_LqrPuSUxcs84bMvQiPD8<br>

GIT REMOTE CONNECTION<br>
https://help.github.com/articles/adding-an-existing-project-to-github-using-the-command-line/<br>
