## Company-shared style guides and practices

### Must be read and applied:
- [node.js style guide](nodejs/node-style-guide.md)
- [angular.js style guide](angularjs/README.md)
- [commit message guideline](contribution/contribution-guidelines.md)
- [git flow](gitflow/readme.md)
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


----


Copyright (c) Year(s), Valor Software <valorkin@gmail.com>

Permission to use, copy, modify, and/or distribute this software for any
purpose with or without fee is hereby granted, provided that the above
copyright notice and this permission notice appear in all copies.

THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES
WITH REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF
MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR
ANY SPECIAL, DIRECT, INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES
WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN
ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING
