# node-normalize-scss

* Forked from: [github.com/akuda/normalize-scss-vanilla](http://github.com/akuda/normalize-scss-vanilla)

This is simply a renamed normalize.css file, suitable for importing with npm and libsass directly. No changes have been made to the actual file.

Based on version 3.0.3

###Install

```
npm install node-normalize-scss --save-dev
```

### Stylesheet usage

Use either method above or for your chosen task runner (gulp.js, Grunt, etc.), then in your stylesheet:

```scss
@import "normalize";
```

## gulp.js Usage

Using the [gulp-sass](https://github.com/dlmanning/gulp-sass) plugin.

```javascript
var gulp = require('gulp');
var sass = require('gulp-sass');

gulp.task('sass', function () {
  gulp.src('path/to/input.scss')
    .pipe(sass({
      // includePaths: require('node-normalize-scss').with('other/path', 'another/path')
      // - or -
      includePaths: require('node-normalize-scss').includePaths
    }))
    .pipe(gulp.dest('path/to/output.css'));
});
```

## Grunt Usage

### Using *grunt-sass*

The [grunt-sass](https://github.com/sindresorhus/grunt-sass) task uses
[node-sass](https://github.com/andrew/node-sass)
([LibSass](https://github.com/hcatlin/libsass)) underneath, and is the recommended
way to use Grunt with node-neat.

Example config:

```javascript
grunt.initConfig({
  sass: {
    dist: {
      options: {
        // includePaths: require('node-normalize-scss').with('other/path', 'another/path')
        // - or -
        includePaths: require('node-normalize-scss').includePaths
      },
      files: {
        'path/to/output.css': 'path/to/input.scss'
      }
    }
  }
});
```
