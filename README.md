-----------------------------------------------------------------------------------------------------------------------------------




This is my first learning of Gulp.js. Gulp.js is a task runner to automate certain tasks in web development.
Here I am using it for transpilling sass codes to regular css which can be used by the browser. I use the node package manager (npm). To use the node package manager, download and install Node.js from the link: https://nodejs.org. Then go into the node command prompt and install Gulp.js.




------------------------------------------------------
To install gulp.js (npm)
------------------------------------------------------



1) Globally:


$ npm install gulp -g


2) Locally:

a) Make a project directory:

$ mkdir my-gulp-project

b) Go into directory:

$ cd my-gulp-project

c) Create a package.json file:

$ npm init

d) Create the node modules for the project:

$ npm install --save-dev gulp


----------------------------------------------
To install Gulp and Node Sass
---------------------------------------------


1) $ npm install node-sass gulp-sass --save-dev

2) Then use it as follows (https://www.npmjs.com/package/gulp-sass):



<!-- ======================================================================== -->

'use strict';

var gulp = require('gulp');
var sass = require('gulp-sass');

sass.compiler = require('node-sass');

gulp.task('sass', function () {
  return gulp.src('./sass/**/*.scss')
    .pipe(sass().on('error', sass.logError))
    .pipe(gulp.dest('./css'));
});

gulp.task('sass:watch', function () {
  gulp.watch('./sass/**/*.scss', ['sass']);
});

<!-- ========================================================================= -->



or

const gulp = require('gulp');
const sass = require('gulp-sass');

sass.compiler = require('node-sass');

gulp.task('sass', () => {
  return gulp.src('./sass/**/*.scss')
    .pipe(sass().on('error', sass.logError))
    .pipe(gulp.dest('./css'));
});

gulp.task('sass:watch', () => {
  gulp.watch('./sass/**/*.scss', ['sass']);
});

<!-- ========================================================================== -->



------------------------------------------------------------------------------------------------------------------------
