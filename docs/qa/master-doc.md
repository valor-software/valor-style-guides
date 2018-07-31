- View: Code configuration
- Entity: tslint.json
- Type: mandatory
- NG
    - Example: https://github.com/valor-software/ngx-bootstrap/blob/development/tslint.json
    - Link: https://github.com/valor-software/tslint-config-valorsoft
- Node
    - Example: https://github.com/cbdr/CBSearchNode/blob/development/tslint.json
    - Link: //TODO
- Short Description: TSLint is an extensible static analysis tool that checks TypeScript code for readability, maintainability, and functionality errors. It is widely supported across modern editors & build systems and can be customized with your own lint rules, configurations, and formatters.
- Human Description:
    - What?: TSLint is a static code analysis tool used in software development for checking Typescript code quality. TSLint checks your TypeScript code for readability, maintainability, and functionality errors. TSLint supports: an extensive set of core rules, custom lint rules, custom formatters (failure reporters), inline disabling and enabling of rules with comment flags in source code, configuration presets (tslint:latest, tslint-react, etc.) and plugin composition, automatic fixing of formatting & style violations
    - What For?: For catching common errors in programming or otherwise confusing constructs that are prone to producing bugs. Provide possibility to save code cleaner, more supportable and in the same style.
    - How?:
    >Note:

    tslint will have to use the same version of tsc used to actually compile your sources files.

    >Details:

    1. https://www.npmjs.com/package/tslint
    2. https://narayanatechnicalworld.blogspot.com/2016/05/what-is-tslint.html
```bash
npm install typescript -g //if you already install typescript, skip it.
npm install tslint

Generate tslint.json config file by just running the below command.
tslint --init
```

---
- View: Code configuration
- Entity: tsconfig.json
- Type: mandatory
- NG
    - Example: https://github.com/valor-software/ngx-bootstrap/blob/development/tsconfig.json
    - Link: https://www.typescriptlang.org/docs/handbook/tsconfig-json.html
- Node
    - Exapmle: https://github.com/cbdr/CBSearchNode/blob/development/tsconfig.json
    - Link: https://www.typescriptlang.org/docs/handbook/tsconfig-json.html
- Short Description: The presence of a tsconfig.json file in a directory indicates that the directory is the root of a TypeScript project. The tsconfig.json file specifies the root files and the compiler options required to compile the project.
- Human Description:
    - What?: Configuration for project compilation.
    - What For?: The tsconfig.json file specifies the root files and the compiler options required to compile the project.
This provide possibilities to compiling project each time the same way for all team, instance, etc.
    - How?: https://www.typescriptlang.org/docs/handbook/tsconfig-json.html
---

- View: Code configuration
- Entity: package.json
- Type: mandatory
- NG
    - Example: https://github.com/valor-software/ngx-bootstrap/blob/development/package.json
    - Link: https://docs.npmjs.com/files/package.json
- Node
    - Exapmle: https://github.com/cbdr/CBSearchNode/blob/development/package.json
    - Link: https://docs.npmjs.com/files/package.json
- Short Description: The most important things in your package.json are the name and version fields as they will be required. The name and version together form an identifier that is assumed to be completely unique. Changes to the package should come along with changes to the version.
- Human Description:
    - What?:
    package.json holds various metadata relevant to the project.
    A package.json file:

      - lists the packages that your project depends on.
      - allows you to specify the versions of a package that your project can use using semantic versioning rules.
      - makes your build reproducible, and therefore much easier to share with other developers.
    - What For?: package.json is used to give information to npm that allows it to identify the project as well as handle the project's dependencies. It can also contain other metadata such as a project description, the version of the project in a particular distribution, license information, even configuration data - all of which can be vital to both npm and to the end users of the package. The package.json file is normally located at the root directory of a Node.js project.
    - How?:
    To create a package.json with values that you supply, run:

        ```bash
         npm init
        ```
      This will initiate a command line questionnaire that will conclude with the creation of a package.json in the directory in which you initiated the command.

      Each propery described in detail [here](https://nodesource.com/blog/the-basics-of-package-json-in-node-js-and-npm/)

---

- View: Code configuration
- Entity: package-lock.json
- Type: mandatory
- NG
    - Example: https://github.com/valor-software/ngx-bootstrap/blob/development/package-lock.json
    - Link: https://docs.npmjs.com/files/package-lock.json
- Node
    - Exapmle:
    - Link: https://docs.npmjs.com/files/package-lock.json
- Short Description: package-lock.json is automatically generated for any operations where npm modifies either the node_modules tree, or package.json. It describes the exact tree that was generated, such that subsequent installs are able to generate identical trees, regardless of intermediate dependency updates.
- Human Description:
    - What?: Autogenerated file that describes the exact tree that was generated, such that subsequent installs are able to generate identical trees, regardless of intermediate dependency updates.
    - What For?: The purpose of the package-lock is to avoid installing modules from the same package.json resulting in two different installs. The idea then becomes that instead of using package.json to resolve and install modules, npm will use the package-lock.json. Because the package-lock specifies a version, location and integrity hash for every module and each of its dependencies, the install it creates will be the same, every single time. It won’t matter what device you are on, or when in the future you install, it should give you the same result every time, which is very useful.
      package-lock.json serves various purposes:
        - Describe a single representation of a dependency tree such that teammates, deployments, and continuous integration are guaranteed to install exactly the same dependencies.

        - Provide a facility for users to "time-travel" to previous states of node_modules without having to commit the directory itself.

        - To facilitate greater visibility of tree changes through readable source control diffs.

        - Optimize the installation process by allowing npm to skip repeated metadata resolutions for previously-installed packages.
    - How?: Generates automatically
---

- View: Code configuration
- Entity: .vcmrc
- Type: optional/mandatory
- NG
    - Example: https://github.com/conventional-changelog-archived-repos/validate-commit-msg/blob/master/.vcmrc
    - Link: https://www.npmjs.com/package/validate-commit-msg
- Node
    - Exapmle: Same
    - Link: Same
- Short Description: Config for commit messages validation
- Human Description:
    - What?: A configuration for script that validates commit messages on each commit according to the specific commit message guidelines.
    - What For?: To streamline and standardize commit messages across the project
    - How?: Configured via .vcmrc. It must be valid JSON file, or via package.json (Note: .vcmrc has precedence, if it does not exist, then package.json will be used.):
      ```
          {
            "config": {
              "validate-commit-msg": {
                /* your config here */
              }
            }
          }
      ```
---

- View: Code configuration
- Entity: .npmrc
- Type: optional
- NG
    - Example: https://github.com/valor-software/ngx-bootstrap/blob/development/.npmrc
    - Link: https://docs.npmjs.com/files/npmrc
- Node
    - Exapmle: Same
    - Link: Same
- Short Description: Config settings for npm
- Human Description:
    - What?: config file from which npm gets its config settings. (it also gets them from)
    - What For?: To update and edit the contents of the npm configuration, for examples see [this article](https://dzone.com/articles/configuring-your-npmrc-for-an-optimal-nodejs-envir-2)
    - How?: ```npm config``` command can be used to update and edit the contents of the user and global npmrc files.
    .npmrc is created when you ```npm login``` but you should be able to simply create a file manually:

      - per-project config file (/path/to/my/project/.npmrc)
      - per-user config file ```(~/.npmrc)```
      - global config file ```($PREFIX/etc/npmrc)```
      - npm builtin config file ```(/path/to/npm/npmrc)```

---

- View: Code configuration
- Entity: .gitignore
- Type: mandatory
- NG
    - Example: https://github.com/valor-software/ngx-bootstrap/blob/development/.gitignore
    - Link: https://git-scm.com/docs/gitignore
- Node
    - Exapmle: Same
    - Link: Same
- Short Description: A gitignore file specifies intentionally untracked files that Git should ignore. Files already tracked by Git are not affected
- Human Description:
    - What?: A gitignore file specifies intentionally untracked files that Git should ignore. Files already tracked by Git are not affected;
    - What For?: To exclude files that are unnecessary or the ones that should not be included in repo for whatever reason
    - How?: manually create and add desired files. Or use https://www.gitignore.io/ and edit it afterwards. Use [this](https://git-scm.com/docs/gitignore) guide for reference

---

- View: Repo Info
- Entity: README.md
- Type: mandatory
- NG
    - Example: https://github.com/valor-software/ngx-bootstrap/blob/development/README.md
    - Link: https://gist.github.com/PurpleBooth/109311bb0361f32d87a2
- Node
    - Exapmle: Same
    - Link: Same
- Short Description: Common document with project description
- Human Description:
    - What?: File in root directory of repository. A README file contains information about other files in a directory or archive of computer software. This is what everyone will see when they get on your repository page. consider writing what you feel important for users in it. List all API references, project description and anything that you would want to know from someone else's repository.
    - What For?: To explain what the project is, its purpose and how to use it. More info [here](https://gist.github.com/jxson/1784669)
    - How?: Just use [this](https://gist.github.com/PurpleBooth/109311bb0361f32d87a2) template

---


- View: Code Configuration
- Entity: .env
- Type: optional
- NG
    - Example: https://www.npmjs.com/package/dotenv
    - Link: https://www.npmjs.com/package/dotenv
- Node
    - Exapmle: Same
    - Link: Same
- Short Description: Dotenv is a zero-dependency module that loads environment variables from a .env file into process.env
- Human Description:
    - What?: A module that loads environment variables from a .env file that you create and adds them to the process.env object that is made available to the application.
    - What For?: To assist in following situation:

      Applications that rely on third-party sources for data will at some point need to include things like OAuth tokens, SSH keys, or API credentials. This becomes an issue when the code for the application gets pushed up to a public facing source control like GitHub. Once the code is up there it is accessible to anyone that sees it. And so are your keys.
    - How?: Add the following line to your app.
      ```
          require('dotenv').config()
      ```
      Then create a .env file at the root directory of your application and add the variables to it.
      ```
          //contents of .env

          SECRET_KEY=abcd1234
      ```
          Finally, add ‘.env’ to your ‘.gitignore’ file so that Git ignores it and it never ends up on GitHub. You can add any keys you want to this file.

          More info [here](https://medium.com/@thejasonfile/using-dotenv-package-to-create-environment-variables-33da4ac4ea8f)

---

- View: Code Configuration
- Entity: .editorconfig
- Type: optional
- NG
    - Example: https://editorconfig.org/#example-file
    - Link: http://editorconfig.org
- Node
    - Exapmle: Same
    - Link: Same
- Short Description: EditorConfig helps developers define and maintain consistent coding styles between different editors and IDEs.
- Human Description:
    - What?: EditorConfig defines coding conventions for groups of files and instructs text editors to adhere to these conventions.
    - What For?: To ease editor config plugins and extensions and settings maintainability
    - How?: Follow the guide on [official wiki](https://github.com/editorconfig/editorconfig/wiki/Plugin-How-To)
---

- View: Code Configuration
- Entity: .angular-cli.json
- Type: mandatory
- NG
    - Example: https://github.com/valor-software/ngx-bootstrap/blob/development/.angular-cli.json.bak
    - Link: https://github.com/angular/angular-cli/wiki/angular-cli
- Node
    - Exapmle: -
    - Link: -
- Short Description: The global configuration of the project.
- Human Description:
    - What?: Config file for Angular CLI
    - What For?: To automate your development workflow. It allows you to:

      - create a new Angular application
      - run a development server with LiveReload support to preview your application during development
      - add features to your existing Angular application
      - run your application’s unit tests
      - run your application’s end-to-end (E2E) tests
      - build your application for deployment to production.
    - How?: Autogenerated after ```ng new your_app``` and/or follow this [guide](https://www.sitepoint.com/ultimate-angular-cli-reference/)
---

- View: CI Configuration
- Entity: Dockerfile
- Type: optional/mandatory
- NG
    - Example:
    - Link: https://docs.docker.com/engine/swarm/configs/
- Node
    - Exapmle: https://github.com/cbdr/CBSearchNode/blob/development/Dockerfile
    - Link: https://docs.docker.com/engine/swarm/configs/
- Short Description: Deployment configuration
- Human Description:
    - What?: A Dockerfile is a text document that contains all the commands a user could call on the command line to assemble an image.
    - What For?: Docker builds images automatically by reading the instructions from a Dockerfile -- a text file that contains all commands, in order, needed to build a given image.
    - How?: Guide to [best practices of writing Dockerfile](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/)
---

- View: CI Configuration
- Entity: Jenkinsfile
- Type: ?
- NG
    - Example:
    - Link:
- Node
    - Exapmle:
    - Link:
- Short Description: Jenkins configuration file that describes automated build process
- Human Description:
    - What?: Configuration file for Jenkins (automation server), which orchestrates the build and manages the resulting outputs through scripted steps.
    - What For?: Jenkinsfile is used to to automate tasks associated with building, testing, and deploying software. The most common basic pipeline described in a Jenkinsfile consists of three stages: Build, Test, and Deploy.
      - The Build stage is typically where source code is assembled, compiled and packaged.
      - The Test stage, crucial to successful CI/CD processes, is enabled by a number of Jenkins plugins that facilitate test execution and results recording, which are visualized in the Web Dashboard UI.
      - The Deployment stage encompasses anything from publishing build artifacts to a management repository to pushing code to pre-production and production environments. Build jobs can be configured to stop upon any step failure, which increases build quality and reliability by not allowing failing code to progress through the deployment process, saving time and resources while reducing risk.
    - How?: Follow [official guide](https://jenkins.io/doc/book/pipeline/jenkinsfile/#creating-a-jenkinsfile) to create a working Jenkinsfile
---

- View: CI Configuration
- Entity: Travis.yml
- Type: ?
- NG
    - Example:
    - Link:
- Node
    - Exapmle:
    - Link:
- Short Description:
- Human Description:
    - What?: Configuration for Travis CI. Travis CI is configured by adding a file named .travis.yml, which is a YAML (YAML 1.1.) format text file, to the root directory of the repository.
    - What For?: To configure build environment, to tell Travis CI what to do and to learn about your project and how you want your builds to be executed.
    - How?: Follow the [official getting started guide](https://docs.travis-ci.com/user/customizing-the-build/)
---

- View: Code Configuration
- Entity: .prettierrc
- Type: optional
- NG
    - Example: https://github.com/valor-software/ngx-bootstrap/blob/development/.prettierrc
    - Link: https://github.com/valor-software/ngx-bootstrap/blob/development/.prettierrc
- Node
    - Exapmle: Same
    - Link: Same
- Short Description: Configuration file for "Prettier" code formatter.
- Human Description:
    - What?: Configuration file for "Prettier" code formatter.
    - What For?: It removes all original styling and ensures that all outputted code conforms to a consistent style.
    Prettier takes your code and reprints it from scratch by taking the line length into account. Prettier enforces a consistent code style (i.e. code formatting that won't affect the AST) across your entire codebase because it disregards the original styling* by parsing it away and re-printing the parsed AST with its own rules that take the maximum line length into account, wrapping code when necessary. Basically it makes your code to adhere the same rules, which is useful while working as as team to maintain same code across the codebase.
    - How?: Follow [official guide](https://prettier.io/docs/en/configuration.html) to configure it (or ask your teammate to provide a valid one)
---

- View: App Documentation
- Entity: CHANGELOG.md
- Type: optional
- NG
    - Example: https://github.com/valor-software/ngx-bootstrap/blob/development/CHANGELOG.md
    - Link: https://www.npmjs.com/package/conventional-changelog-cli
- Node
    - Exapmle: Same
    - Link: Same
- Short Description: A changelog is a file which contains a curated, chronologically ordered list of notable changes for each version of a project.
- Human Description:
    - What?: A changelog is a file which contains a curated, chronologically ordered list of notable changes for each version of a project.
    - What For?: To make it easier for users and contributors to see precisely what notable changes have been made between each release (or version) of the project.
    - How?: https://keepachangelog.com/
---

- View: Repo Info
- Entity: CODE_OF_CONDUCT.md
- Type: optional/mandatory
- NG
    - Example: https://github.com/valor-software/ngx-bootstrap/blob/development/CODE_OF_CONDUCT.md
    - Link: For opensource only
- Node
    - Exapmle: Same
    - Link: Same
- Short Description: A code of conduct is a set of rules outlining the social norms, religious rules and responsibilities of, and or proper practices for, an individual.
- Human Description:
    - What?: A code of conduct is a set of rules outlining the social norms, religious rules and responsibilities of, and or proper practices for, an individual.
    - What For?: A well-written code of conduct clarifies an organization's mission, values and principles, linking them with standards of professional conduct. The code articulates the values the organization wishes to foster in leaders and employees and, in doing so, defines desired behavior. As a result, written codes of conduct or ethics can become benchmarks against which individual and organizational performance can be measured.
    Externally, a code serves several important purposes:

      - Compliance: Legislation (i.e., the Sarbanes-Oxley Act of 2002) requires individuals serving on boards and organizational leaders of public companies to implement codes or clearly explain why they have not.
      - Marketing: A code serves as a public statement of what the company stands for and its commitment to high standards and right conduct.
      - Risk Mitigation: Organizations with codes of ethics, and who follow other defined steps in the U.S. Sentencing Commission's Federal Sentencing Guidelines, can reduce the financial risks associated with government fines for ethical misconduct by demonstrating they have made a "good faith effort" to prevent illegal acts.
    - How?: Read and grab one from [our repo](https://github.com/valor-software/ngx-bootstrap/blob/development/CODE_OF_CONDUCT.md)
---

- View: Repo Info
- Entity: CONTRIBUTING.md
- Type: optional/mandatory
- NG
    - Example: https://github.com/valor-software/ngx-bootstrap/blob/development/CONTRIBUTING.md
    - Link: For opensource only
- Node
    - Exapmle: Same
    - Link: Same
- Short Description:
- Human Description:
    - What?: CONTRIBUTING.md is a file in the root repo directory. It explains how a participant should do things like format code, test fixes, and submit patches.
    - What For?: From a maintainer’s point of view, the document succinctly communicates how best to collaborate. And for a contributor, one quick check of this file verifies their submission follows the maintainer’s guidelines.
    - How?: [Official GitHub Blog](https://blog.github.com/2012-09-17-contributing-guidelines/) describing everything about Contributing file and ideology behind it. And read(!) and grab our rules [from here](https://github.com/valor-software/ngx-bootstrap/blob/development/CONTRIBUTING.md)
---

- View: Repo Info
- Entity: LICENSE
- Type: optional/mandatory
- NG
    - Example: https://github.com/valor-software/ngx-bootstrap/blob/development/LICENSE
    - Link: For opensource only(?)
- Node
    - Exapmle: -
    - Link: -
- Short Description: https://help.github.com/articles/licensing-a-repository/#disclaimer
- Human Description:
    - What?: File with a license that defines a set of rules on which this code in this specific repository can be used.
    - What For?: Public repositories on GitHub are often used to share open source software. For your repository to truly be open source, you'll need to license it so that others are free to use, change, and distribute the software.
    - How?: Read an [official github guide](https://help.github.com/articles/licensing-a-repository/) to choose an appropriate license or use this service https://tldrlegal.com
---

- View: Repo Info
- Entity: CODEOWNERS
- Type: mandatory
- NG
    - Example: https://github.com/cbdr/CBSearchNode/blob/development/.github/CODEOWNERS
    - Link: https://help.github.com/articles/about-codeowners/
- Node
    - Exapmle: Same
    - Link: Same
- Short Description: Codeowners of the repository
- Human Description:
    - What?: CODEOWNERS is a file that defines individuals or teams that are responsible for code in a repository.
    - What For?: To set boundaries of who is responsible for what. Each CODEOWNERS file assigns the code owners for a single branch in the repository. Thus, you can assign different code owners for different branches, such as @octo-org/codeowners-team for a code base on the master branch and @octocat for a GitHub Pages site on the gh-pages branch.
    - How?: Follow the [Official GitHub guide](https://help.github.com/articles/about-codeowners/) on this matter.
---

- View: Repo Info
- Entity: PULL_REQUEST_TEMPLATE
- Type: mandatory
- NG
    - Example: https://github.com/valor-software/ngx-bootstrap/blob/development/.github/PULL_REQUEST_TEMPLATE.md
    - Link: https://blog.github.com/2016-02-17-issue-and-pull-request-templates/
- Node
    - Exapmle: Same
    - Link: Same
- Short Description:
- Human Description:
    - What?: These templates auto-populate the issue/pull-request description field and provide a skeleton framework that you can fill out.
    - What For?: When you add a pull request template to your repository, project contributors will automatically see the template's contents in the pull request body. All this is done to achieve consistency and it becomes easier to maintain code
    - How?: More info [in this blogpost](https://embeddedartistry.com/blog/2017/8/4/a-github-pull-request-template-for-your-projects) and [in this](https://help.github.com/articles/creating-a-pull-request-template-for-your-repository/), but generally, just grab [one of ours](https://github.com/valor-software/ngx-bootstrap/blob/development/.github/PULL_REQUEST_TEMPLATE.md). To add an PR template to a repository create a file called PULL_REQUEST_TEMPLATE in the root directory.
---

- View: Repo Info
- Entity: ISSUE_TEMPLATE
- Type: mandatory
- NG
    - Example: https://github.com/valor-software/ngx-bootstrap/blob/development/.github/ISSUE_TEMPLATE.md
    - Link: https://blog.github.com/2016-02-17-issue-and-pull-request-templates/
- Node
    - Exapmle: Same
    - Link: Same
- Short Description: Template for issues
- Human Description:
    - What?: A template for unifying issues submission to the project
    - What For?: It’s hard to solve a problem when important details are missing. Now project maintainers can add templates for Issues and Pull Requests to projects, helping contributors share the right details at the start of a thread.
    - How?: To add an Issue template to a repository create a file called ISSUE_TEMPLATE in the root directory. More info [in this blogpost](https://embeddedartistry.com/blog/2017/8/4/a-github-pull-request-template-for-your-projects) and [in this](https://help.github.com/articles/creating-a-pull-request-template-for-your-repository/), but generally, just grab [one of ours](https://github.com/valor-software/ngx-bootstrap/blob/development/.github/ISSUE_TEMPLATE.md)
---

- View: Test Configuration
- Entity: jasmine.json
- Type: optional
- NG
    - Example: https://github.com/cbdr/CBSearchNode/blob/development/spec/support/jasmine.json
    - Link: https://jasmine.github.io/setup/nodejs.html
- Node
    - Exapmle: https://github.com/cbdr/CBSearchNode/blob/development/spec/support/jasmine.json
    - Link: https://jasmine.github.io/setup/nodejs.html
- Short Description: Configuration for API Tests/Unit Server Tests
- Human Description:
    - What?: Configuration file for running Jasmine tests for node-based projects.
    - What For?: To enumerate the source files and spec files you would like the Jasmine runner to include. Basically after initializing the project jasmine creates a spec directory and configuration json for you. The spec directory is used to store all your test files. By doing this, jasmine will know where all your tests are, and then can execute them accordingly. The JSON file is used to store specific configuration information about jasmine.
    - How?: File is created after initializing the project: run 'jasmine init', edit spec/support/jasmine.json appropriately. Follow [this](https://www.guru99.com/node-js-testing-jasmine.html) guide if any questions
---

- View: Test Configuration
- Entity: karma.conf.js
- Type: mandatory
- NG
    - Example: https://github.com/valor-software/ngx-bootstrap/blob/development/karma.conf.js
    - Link: http://karma-runner.github.io/2.0/intro/configuration.html
- Node
    - Exapmle: -
    - Link: -
- Short Description: Unit test runner for NG projects
- Human Description:
    - What?: In order to serve you well, Karma needs to know about your project in order to test it and this is done via a configuration file.
    - What For?: This is a master configuration file to configure all test options, watchers, directories, browser, etc.
    - How?: ile is generated after initializing karma by running 'karma init':

      The Karma configuration file can be written in JavaScript, CoffeeScript, or TypeScript and is loaded as a regular Node.js module.

      Unless provided as argument, the Karma CLI will look for a configuration file at
  ```
          ./karma.conf.js
          ./karma.conf.coffee
          ./karma.conf.ts
          ./.config/karma.conf.js
          ./.config/karma.conf.coffee
          ./.config/karma.conf.ts
  ```
      Follow [official guide](http://karma-runner.github.io/2.0/config/configuration-file.html) to get more info

---

- View: Test Configuration
- Entity: protractor.conf.js
- Type: optional/mandatory
- NG
    - Example: https://github.com/ludmilanesvitiy/ProtractorExample/blob/master/protractor.conf.js
    - Link: https://github.com/angular/protractor/blob/master/lib/config.ts
- Node
    - Exapmle: -
    - Link: -
- Short Description: Configuration for e2e tests
- Human Description:
    - What?: Configuration file for e2e test-runner Protractor. Protractor needs two files to run, a spec file and a configuration file.
    - What For?: Master configuration file, everything is defined there: framework, spec files, selenium address, browser, timeouts, etc!
    - How?: Use [default template](https://raw.githubusercontent.com/angular/protractor/master/example/conf.js) and edit it accordingly, + [official guide](https://www.protractortest.org/#/tutorial) to get more info
---

- View: Test Configuration
- Entity: wallaby.js
- Type: optional
- NG
    - Example: https://github.com/valor-software/ngx-bootstrap/blob/development/wallaby.js
    - Link: https://wallabyjs.com/
- Node
    - Exapmle: -
    - Link: -
- Short Description: Integrated Continuous Testing Tool for JavaScript
- Human Description:
    - What?: Wallaby.js is an integrated continuous testing tool for JavaScript. It is great for doing JavaScript TDD (Test-driven development) or BDD (Behavior Driven Development), but it works great for other approaches as well.
    - What For?: t runs your tests immediately as you change your code (you don’t even have to save the file) and displays various results (including the code coverage, error and console messages) right inside your code editor, next to your code.
    - How?: It works as a plugin for your code editor:


      - JetBrains IDEs (WebStorm, IntelliJ IDEA, PhpStorm, RubyMine, or PyCharm
      - Visual Studio Code;
      - Atom text editor;
      - Visual Studio;
      - Sublime Text;
      - Wallaby App.

      Follow [official guide](https://wallabyjs.com/docs/intro/config.html) to configure wallaby.js
---

- View: Test Configuration
- Entity: cypress.json
- Type: optional/mandatory
- NG
    - Example: https://github.com/valor-software/ngx-bootstrap/blob/development/cypress.json
    - Link: https://www.cypress.io/
- Node
    - Exapmle: -
    - Link: -
- Short Description: Configuration for e2e tests
- Human Description:
    - What?: Cypress configuration file that is used to store the projectId (after configuring your tests to record) and any configuration values you supply.
    - What For?: To configure e2e test runner. It contains Global options, such as  environment variables, ignored test files, etc. Timeouts, Folders / Files settings, Screenshots / Videos options.
    - How?: When a project is added to Cypress, a cypress.json file is created in the project. Learn more about cypress.json parameters in [official guide](https://docs.cypress.io/guides/references/configuration.html)
---

- View: App Documentation
- Entity: typedoc.js
- Type: optional
- NG
    - Example: https://github.com/valor-software/ngx-bootstrap/blob/development/typedoc.js
    - Link: https://www.npmjs.com/package/typedoc + https://www.npmjs.com/package/@compodoc/compodoc
- Node
    - Exapmle: Same
    - Link: Same
- Short Description: Documentation generator for TypeScript projects.
- Human Description:
    - What?: Documentation generator for TypeScript projects.
    - What For?: To autogenerate documentation for TypeScript projects.
    - How?: Follow [these](https://github.com/TypeStrong/typedoc) [two](http://typedoc.org/guides/usage/) official guides.
---

- View: Test Configuration
- Entity: wait-for-it.sh
- Type: optional
- NG
    - Example: -
    - Link: -
- Node
    - Exapmle: https://github.com/cbdr/CBSearchNode/blob/development/wait-for-it.sh
    - Link:
- Short Description: Bash script that will wait on the availability of a host and TCP port
- Human Description:
    - What?: wait-for-it.sh is a pure bash script that will wait on the availability of a host and TCP port.
    - What For?: It is useful for synchronizing the spin-up of interdependent services, such as linked docker containers. Since it is a pure bash script, it does not have any external dependencies.
    - How?: to see if we can access port 80 on www.google.com, and if it is available, echo the message google is up.
    ```bash
    $ ./wait-for-it.sh www.google.com:80 -- echo "google is up"
wait-for-it.sh: waiting 15 seconds for www.google.com:80
wait-for-it.sh: www.google.com:80 is available after 0 seconds
google is up
    ```

---


- View: Code Configuration
- Entity: .pem files
- Type: mandatory
- NG
    - Example: -
    - Link: -
- Node
    - Exapmle: -
    - Link: -
- Short Description: Sertificates for local development, using https
- Human Description:
    - What?:
    - What For?:
    - How?:
---

- View: CI Configuration
- Entity: .dockerignore
- Type: optional
- NG
    - Example: -
    - Link: -
- Node
    - Exapmle: -
    - Link: -
- Short Description: configuration file that helps to exclude files from the build
- Human Description:
    - What?: .dockerignore file is the tool, that can help you to define the Docker build context you really need.
    - What For?: to exclude files and directories that match patterns in it.  This helps to avoid unnecessarily sending large or sensitive files and directories to the daemon and potentially adding them to images
    - How?: For information about how to create a .dockerignore file see the [this official guide](https://docs.docker.com/engine/reference/builder/#dockerignore-file) and [this one](https://codefresh.io/docker-tutorial/not-ignore-dockerignore/)
---
