# VelocityCSS

Velocity: A Fast, Simple, Responsive CSS Framework

![Screenshot 2023-08-21 223536](https://github.com/pratikt76/VelocityCSS/assets/96099806/795224a5-3e1b-4c9e-9b0e-4117418eda0e)
![Screenshot 2023-08-21 223554](https://github.com/pratikt76/VelocityCSS/assets/96099806/fea5994e-f3b4-446a-b5fd-f7f14071a2b8)
![Screenshot 2023-08-21 223605](https://github.com/pratikt76/VelocityCSS/assets/96099806/6e9f865b-04e7-4ba8-bc59-542b73945772)

To Purge the CSS {index.css}
Paste following code in gulpfile.js

```
const { src, dest, watch, series } = require('gulp')
const sass = require('gulp-sass')(require('sass'))
const purgecss = require('gulp-purgecss')

function buildStyles() {
  return src('shinobi/**/*.scss')
    .pipe(sass({ outputStyle: 'compressed' }))
    .pipe(purgecss({ content: ['*.html'] }))
    .pipe(dest('css'))
}

function watchTask() {
  watch(['shinobi/**/*.scss'], buildStyles)
}

exports.default = series(buildStyles, watchTask)
```
