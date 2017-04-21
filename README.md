# npmtest-voca

#### basic test coverage for  [voca (v1.3.0)](https://vocajs.com)  [![npm package](https://img.shields.io/npm/v/npmtest-voca.svg?style=flat-square)](https://www.npmjs.org/package/npmtest-voca) [![travis-ci.org build-status](https://api.travis-ci.org/npmtest/node-npmtest-voca.svg)](https://travis-ci.org/npmtest/node-npmtest-voca)

#### The ultimate JavaScript string library

[![NPM](https://nodei.co/npm/voca.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/voca)

| git-branch : | [alpha](https://github.com/npmtest/node-npmtest-voca/tree/alpha)|
|--:|:--|
| coverage : | [![istanbul-coverage](https://npmtest.github.io/node-npmtest-voca/build/coverage.badge.svg)](https://npmtest.github.io/node-npmtest-voca/build/coverage.html/index.html)|
| test-report : | [![test-report](https://npmtest.github.io/node-npmtest-voca/build/test-report.badge.svg)](https://npmtest.github.io/node-npmtest-voca/build/test-report.html)|
| build-artifacts : | [![build-artifacts](https://npmtest.github.io/node-npmtest-voca/glyphicons_144_folder_open.png)](https://github.com/npmtest/node-npmtest-voca/tree/gh-pages/build)|

- [https://npmtest.github.io/node-npmtest-voca/build/coverage.html/index.html](https://npmtest.github.io/node-npmtest-voca/build/coverage.html/index.html)

[![istanbul-coverage](https://npmtest.github.io/node-npmtest-voca/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fcoverage.lib.html.png)](https://npmtest.github.io/node-npmtest-voca/build/coverage.html/index.html)

- [https://npmtest.github.io/node-npmtest-voca/build/test-report.html](https://npmtest.github.io/node-npmtest-voca/build/test-report.html)

[![test-report](https://npmtest.github.io/node-npmtest-voca/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Ftest-report.html.png)](https://npmtest.github.io/node-npmtest-voca/build/test-report.html)

- [https://npmdoc.github.io/node-npmdoc-voca/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-voca/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-voca/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-voca/build/apidoc.html)

![npmPackageListing](https://npmtest.github.io/node-npmtest-voca/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmtest.github.io/node-npmtest-voca/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "name": "voca",
    "version": "1.3.0",
    "description": "The ultimate JavaScript string library",
    "homepage": "https://vocajs.com",
    "author": {
        "name": "Dmitri Pavlutin",
        "url": "https://rainsoft.io/about-me/"
    },
    "license": "MIT",
    "keywords": [
        "string",
        "sprintf",
        "trim",
        "truncate",
        "pad",
        "slugify",
        "latinise",
        "escape",
        "word",
        "wrap",
        "case",
        "strip"
    ],
    "repository": {
        "type": "git",
        "url": "git+https://github.com/panzerdp/voca.git"
    },
    "bugs": {
        "url": "https://github.com/panzerdp/voca/issues"
    },
    "main": "index.js",
    "jsnext:main": "index.es2015.js",
    "scripts": {
        "eslint": "eslint . --ext .js",
        "build": "npm run build-dist && npm run build-npm-package",
        "build-dist": "rollup -c config/rollup_dist.js && rollup -c config/rollup_dist_min.js && rollup -c config/rollup_test.js",
        "build-npm-package": "npm run prepare-npm-package && rollup -c config/rollup_dist_mod.js && node config/transform.js && rollup -c config/rollup_dist_es.js",
        "prepare-npm-package": "rm -rf dist_mod && mkdir dist_mod && cp package.json README.md LICENSE.md ./dist_mod",
        "test": "mocha test/index.js --reporter dot",
        "test-npm-package": "mocha test/modules_common.js test/modules_es2015.js --reporter dot",
        "test-sl": "grunt --gruntfile ./test_runner/gruntfile.js --base .",
        "coverage": "istanbul cover _mocha -- test/index.js --reporter spec",
        "report-coverage": "cat ./coverage/lcov.info | codecov",
        "verify": "npm run eslint && npm run coverage",
        "jsdoc": "jsdoc --configure .jsdoc.json",
        "deploy": "rollup -c config/rollup_dist.js && cp dist/voca.js docs/scripts && scp -r docs/* rainishere:/home/rainishere/webapps/voca_docs",
        "precommit": "npm run eslint && npm run test"
    },
    "devDependencies": {
        "babel-cli": "6.22.2",
        "babel-core": "6.22.1",
        "babel-eslint": "7.1.1",
        "babel-plugin-add-module-exports": "0.2.1",
        "babel-plugin-module-resolver": "2.5.0",
        "babel-plugin-transform-es2015-block-scoping": "6.22.0",
        "babel-plugin-transform-es2015-destructuring": "6.22.0",
        "babel-plugin-transform-es2015-modules-commonjs": "6.22.0",
        "babel-plugin-transform-es2015-parameters": "6.22.0",
        "babel-plugin-transform-es2015-shorthand-properties": "6.22.0",
        "babel-plugin-transform-es2015-spread": "6.22.0",
        "babel-plugin-transform-object-assign": "6.22.0",
        "babel-register": "6.22.0",
        "babel-root-import": "4.1.8",
        "chai": "3.5.0",
        "codecov.io": "0.1.6",
        "eslint": "3.15.0",
        "glob": "7.1.1",
        "grunt": "1.0.1",
        "grunt-contrib-connect": "1.0.2",
        "grunt-saucelabs": "9.0.0",
        "husky": "0.13.1",
        "istanbul": "1.1.0-alpha.1",
        "jsdoc": "3.4.3",
        "mkdirp": "0.5.1",
        "mocha": "3.2.0",
        "rollup": "0.41.4",
        "rollup-plugin-babel": "2.7.1",
        "rollup-plugin-uglify": "1.0.1",
        "source-map-support": "0.4.11"
    },
    "dependencies": {}
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
