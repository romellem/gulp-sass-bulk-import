gulp-sass-bulk-import
=====================

> **NOTE:**  
> Forked from [mathisonian/gulp-sass-bulk-import)](https://github.com/mathisonian/gulp-sass-bulk-import) to upgrade the underlying dependencies.
> 
> This upgrade changes the minimum node version needed, from 0.10 to **8.X**.

gulp task to allow importing directories in your SCSS

[![Build Status](https://travis-ci.org/mathisonian/gulp-sass-bulk-import.svg?branch=master)](https://travis-ci.org/mathisonian/gulp-sass-bulk-import)

## installation

```
npm install --save-dev gulp-sass-bulk-import
```


## usage


#### in your .scss file

```scss

@import "some/path/*";

// becomes
// @import "some/path/file1.scss";
// @import "some/path/file2.scss";
// ...

```

#### in your gulpfile

```js
var bulkSass = require('gulp-sass-bulk-import');

gulp.task('css', function() {
    return gulp
            .src(srcDir + 'stylesheets/app.scss')
            .pipe(bulkSass())
            .pipe(
                sass({
                    includePaths: ['src/stylesheets']
                }))
            .pipe( gulp.dest('./public/css/') );
});
```
