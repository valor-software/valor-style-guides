valor-style-guides
=================

# Company-shared style guides and practices

##Must be read and applied: 
- [node.js](nodejs/node-style-guide.md)
- angular.js style guides
- [commit message guideline](contribution/contribution-guidelines.md)
- use [`eslint`](https://github.com/eslint/eslint) and knew `eslint` [rules](http://eslint.org/docs/rules)



### Apply linter rules to your projects:
* [.eslintrc](.eslintrc) - docs for  [eslint](http://eslint.org/docs/rules/)
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

### Editor config rules
* [.editorconfig](https://github.com/valor-software/valor-style-guides/blob/master/.editorconfig)

### Force testing linting:
* [pre-commit](https://www.npmjs.com/package/pre-commit)

Credits: 
* [eslint docs](http://eslint.org/docs/developer-guide/contributing.html)
