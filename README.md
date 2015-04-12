## Company-shared style guides and practices

### Must be read and applied: 
- [node.js style guide](nodejs/node-style-guide.md)
- [angular.js style guide](angularjs/README.md)
- [commit message guideline](contribution/contribution-guidelines.md)

- Code linting: [`eslint`](https://github.com/eslint/eslint)


### Apply linter rules to your projects:
* ESLint options file: [.eslintrc](.eslintrc)
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

### Credits: 
* [eslint docs](http://eslint.org/docs/developer-guide/contributing.html)
