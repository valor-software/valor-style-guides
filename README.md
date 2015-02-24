valor-style-guides
=================

Company-shared style guides and practices

### [node.js style guide](https://github.com/valor-software/valor-style-guides/blob/master/node-style-guide.md)

### Apply linter rules to your projects:
* [.eslintrc](https://github.com/valor-software/valor-style-guides/blob/master/.eslintrc) - docs for  [eslint](http://eslint.org/docs/rules/)
```js
var eslint = require('gulp-eslint');

gulp.task('lint', function () {
  return gulp
    .src(['**/*.js', '!node_modules'])
    .pipe(eslint({useEslintrc: true}))
    .pipe(eslint.format())
    .pipe(eslint.failOnError());
});
```
* ~~[.jshintrc](https://github.com/valor-software/valor-style-guides/blob/master/.jshintrc) - docs for  [jshint](http://jshint.com/docs/)~~
* ~~[.jscs.json](https://github.com/valor-software/valor-style-guides/blob/master/.jscs.json) - docs for   [jscs](http://jscs.info/rules.html)~~

### Editor config rules
* [.editorconfig](https://github.com/valor-software/valor-style-guides/blob/master/.editorconfig)
