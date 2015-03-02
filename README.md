valor-style-guides
=================

Company-shared style guides and practices
Must be read and applied: 
- node.js\angular.js style guides
- commit message guideline
- use eslint and knew eslint rules

### Commit message guideline

#### Important
* commits without task id (link for asana) are not allowed

Make the changes to the code and tests and then commit to your branch. Be sure to follow the commit message conventions.

Commit message summaries must follow this basic format:

```
Tag: Message [Action #1234]
```

The `Tag` is one of the following:
* `Fix` - for a bug fix.
* `Update` - for a backwards-compatible enhancement.
* `Breaking` - for a backwards-incompatible enhancement.
* `Docs` - changes to documentation only.
* `Build` - changes to build process only.
* `New` - implemented a new feature.
* `Upgrade` - for a dependency upgrade.

`Message` is short description of what have been done
`Action` - depends on used task tracking, but in general case:
* `refs` - link commit to task
* `fixes` - closes task, moving it to testing state

The message summary should be a one-sentence description of the change. The issue number should be mentioned at the end. If the commit doesn't completely fix the issue, then use `[refs #1234]` instead of `[fixes #1234]`.

Here are some good commit message summary examples:

```
Build: Update Travis to only test Node 0.10 [refs #734]
Fix: Semi rule incorrectly flagging extra semicolon [fixes #840]
Upgrade: Esprima to 1.2, switch to using Esprima comment attachment [fixes #730]
```

The commit message format is important because these messages are used to create a changelog for each release. The tag and issue number help to create more consistent and useful changelogs.



### Code style guides:
* [node.js style guide](node-style-guide.md)

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
* ~~[.jshintrc](https://github.com/valor-software/valor-style-guides/blob/master/.jshintrc) - docs for  [jshint](http://jshint.com/docs/)~~
* ~~[.jscs.json](https://github.com/valor-software/valor-style-guides/blob/master/.jscs.json) - docs for   [jscs](http://jscs.info/rules.html)~~

### Editor config rules
* [.editorconfig](https://github.com/valor-software/valor-style-guides/blob/master/.editorconfig)

### Force testing linting:
* [pre-commit](https://www.npmjs.com/package/pre-commit)

Credits: 
* [eslint docs](http://eslint.org/docs/developer-guide/contributing.html)
