Getting started
node -v

mkdir pcss && cd pcss

npm init -y

npm install gulp gulp-postcss --save-dev

create folder css

***************************************
gulpfile.js

var postcss = require('gulp-postcss');
var gulp = require('gulp');
var autoprixer = require('autoprefixer');
var cssnano = require('cssnano');

gulp.task('serve', ['css'], function() {
  gulp.watch("./css/*.css", ['css']);
});

gulp.task('css', function() {
  var plugin = [
    autoprefixer(),
    cssnano()
  ];
  return gulp.src('./css/*.css')
    .pipe(postcss(plugin))
    .pipe(gulp.dest('./dest'));
 });

//Permet de juste tapper gulp dans la command line pour runner 
gulp.task('default', ['serve']);


*****************************************
//Pour installer des plugins
npm install autoprefixer --save-dev

npm i cssnano --save-dev


















