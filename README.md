# Run MI portal tests on Mac
mvn clean verify -Dusername=evan.scharfer@slalom.com -Dpassword= -Durl=https://mi-portal.sand.gmatas.net/ -Ddriver=src/test/java/com/mwp/abbmi/resources/other/chromedriver -Dcucumber.options=src/test/java/com/mwp/abbmi/resources/features/stabilityToolHumira.feature

# Run MI portal tests on PC
mvn clean verify -Dusername=evan.scharfer@slalom.com -Dpassword= -Durl=https://mi-portal.sand.gmatas.net/ -Ddriver=src/test/java/com/mwp/abbmi/resources/other/chromedriver.exe -Dcucumber.options=src/test/java/com/mwp/abbmi/resources/features/stabilityToolHumira.feature

# Run Puppeteer
JWT=value jest ./tests/puppeteer/manual/adverseEvent/aerInfo/aerInfoConditionals.spec.js

# To run tests in other environment\

* `export BACKEND_ENV={whatever environment you want to test against (sand|test|rfqa|train|beta|slqa)}`
* `yarn build` or if need to test custom schema: `yarn build --env.schemaCase=schema-name-case --env.schemaTask=schema-name-task`
* `yarn test-build`

#### In another terminal window:

* `export BACKEND_ENV={whatever environment you want to test against (sand|test|rfqa|train|beta|slqa)}`
* `export JWT={insert your JWT for **the appropriate env**}`
* `yarn puppeteer`

### Running a single puppeteer test 
* JWT={your jwt} node_modules/.bin/jest tests/puppeteer/manual/{path to spec}

### Mocks

The [mocks server](./mocks/server) directory contains a thin ExpressJS server for mocking external services.

The application can be run in development mode _with mocks_ by using the following command:

```bash
yarn start:mocks
```

This will both start a mocks server and instruct the client to use [mock API endpoints](./src/config/values.js#L6).

### Unit tests

`yarn test`

### Test coverage of unit tests

`yarn test-cov`

### Functional tests

* [Functional tests](./tests/puppeteer/README.md)
* Obtain a JWT by running the app in dev mode, logging in,
  then running this bookmarklet:
  `javascript:(function() {var jwt = sessionStorage.getItem('Ⅲ_session').split('&')[0].split('=').pop();var ta = document.createElement('textarea');var sel = document.getSelection();ta.textContent = jwt;document.body.appendChild(ta);sel.removeAllRanges();ta.select();document.execCommand('copy');sel.removeAllRanges();document.body.removeChild(ta);})()`.
* Run `JWT=* yarn puppeteer`

# New Repo

Go to Github.com
New Repository
Open Terminal
Navigate to a parent directory for your repo
echo "# pilot" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/rolandphillips/pilot.git
git push -u origin master

# Update a file
git add README.md
git commit -m “second commit"
git push -u origin master

# Checkout a branch and add to Github
Git checkout -b branch1
Edit a file
Git add file
git commit -m "branch commit"
git push origin branch1    ///branch is added into GitHub
PR the branch and merge into master