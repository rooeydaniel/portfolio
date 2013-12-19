# The seed for Portfolio project

This project is an application skeleton for your portfolio Web app.  It uses the Bower package manager to handle
front-end dependencies, NodeJS to handle the Web server and Karma (a NodeJS dependency) to run unit tests.

## How to use portfolio-seed

- Create an empty repository at GitHub (maybe portfolio)
- Open up your terminal
- Run the following commands

```
cd /tmp # make sure this is a directory that exists
git clone --bare git@github.com:DojoDevCamp/portfolio-seed.git
cd portfolio-seed.git
git push --mirror git@github.com:portfolio.git # this will be different for you
cd ..
rm -rf portfolio-seed.git
```

### Running the app during development

* Make sure that NodeJS is installed
* From the CLI, in the project directory, run `npm install`

You can run the NodeJS server in two ways:

* Run `scripts/web-server.js` from the CLI
* Inside PyCharm, set up a NodeJS configuration

Then navigate your browser to `http://localhost:<port>/app/index.html` to see the app running in
your browser.

### Running the app in production (Heroku)

* run the heroku_push.sh script
** chmod u+x heroku_push.sh
** ./heroku_push.sh "Commit message"
*** Note that the message you create will get pushed to Heroku and to GitHub, so make it worthwhile

### Running unit tests

Requires [node.js](http://nodejs.org/), Karma (`sudo npm install -g karma`) and a local
or remote browser.

* start `scripts/test.sh` (on windows: `scripts\test.bat`)
  * a browser will start and connect to the Karma server (Chrome is default browser, others can be captured by loading the same url as the one in Chrome or by changing the `config/karma.conf.js` file)
* to run or re-run tests just change any of your source or test javascript files

### End to end testing

Angular ships with a baked-in end-to-end test runner that understands angular, your app and allows
you to write your tests with jasmine-like BDD syntax.

Requires a webserver, node.js + `./scripts/web-server.js` or your backend server that hosts the angular static files.

Check out the
[end-to-end runner's documentation](http://docs.angularjs.org/guide/dev_guide.e2e-testing) for more
info.

* create your end-to-end tests in `test/e2e/scenarios.js`
* serve your project directory with your http/backend server or node.js + `scripts/web-server.js`
* to run do one of:
  * open `http://localhost:port/test/e2e/runner.html` in your browser
  * run the tests from console with [Karma](http://karma-runner.github.io) via
    `scripts/e2e-test.sh` or `script/e2e-test.bat`

## Directory Layout

    .bowerrc                    --> Configures bower to install components under app/lib
    .gitignore                  --> Artifacts we do not want in our git repositories, switched based on where we are pushing changes
    .gitignore.github           --> Master .gitignore for GitHub
    .gitignore.heroku           --> Master .gitignore for Heroku, needed so that we don't push the test scripts
    bower.json                  --> Declares front-end dependencies, like angular and bootstrap
    heroku_push.sh              --> Bash script that makes sure that only appropriate files are pushed to Heroku
    LICENSE                     --> Officially declaring this code under MIT licenses
    package.json                --> Declares dev and prod dependencies, for prod it will install bower
    Procfile                    --> File required by Heroku to launch your application
    README.md                   --> This file

    app/                        --> all of the files to be used in production
      css/                      --> css files
        app.css                 --> default stylesheet
      img/                      --> image files
        portfolio-one.gif       --> Cheetos image for the portfolio page
      index.html                --> app layout file (the main html template file of the app)
      js/                       --> javascript files
        app.js                  --> angular application config, run and routes
        constants.js            --> angular constants
        controllers.js          --> angular controller portion of MVC
        directives.js           --> angular directives, contains a 'toggling' example
      json/
        portfolio-data.json     --> contains dummy portfolio data that can be updated
      partials/                 --> angular view partials (partial html templates)
        about.tpl.html          --> contains the about page content, demonstrates angularjs filters
        contact.tpl.html        --> contains the contact page content
        home.tpl.html           --> contains the home page content
        portfolio.tpl.html      --> contains the portfolio page content, demonstrates angularjs data binding, looping and JSON consumption

    config/karma.conf.js        --> config file for running unit tests with Karma
    config/karma-e2e.conf.js    --> config file for running e2e tests with Karma

    scripts/            --> handy shell/js/ruby scripts
      e2e-test.sh       --> runs end-to-end tests with Karma (*nix)
      e2e-test.bat      --> runs end-to-end tests with Karma (windows)
      test.bat          --> autotests unit tests with Karma (windows)
      test.sh           --> autotests unit tests with Karma (*nix)
      web-server.js     --> simple development webserver based on node.js

    test/               --> test source files and libraries
      e2e/              -->
        runner.html     --> end-to-end test runner (open in your browser to run)
        scenarios.js    --> end-to-end specs
      lib/
        angular/                --> angular testing libraries
          angular-mocks.js      --> mocks that replace certain angular services in tests
          angular-scenario.js   --> angular's scenario (end-to-end) test runner library
          version.txt           --> version file
      unit/                     --> unit level specs/tests
        controllersSpec.js      --> specs for controllers
        directivessSpec.js      --> specs for directives
        filtersSpec.js          --> specs for filters
        servicesSpec.js         --> specs for services

## Contact

For more information, please contact the instructor
