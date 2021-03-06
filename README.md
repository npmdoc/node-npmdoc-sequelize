# npmdoc-sequelize

#### api documentation for  [sequelize (v3.30.4)](https://github.com/sequelize/sequelize#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-sequelize.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-sequelize) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-sequelize.svg)](https://travis-ci.org/npmdoc/node-npmdoc-sequelize)

#### Multi dialect ORM for Node.JS/io.js

[![NPM](https://nodei.co/npm/sequelize.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/sequelize)

- [https://npmdoc.github.io/node-npmdoc-sequelize/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-sequelize/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-sequelize/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-sequelize/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-sequelize/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-sequelize/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Sascha Depold"
    },
    "bugs": {
        "url": "https://github.com/sequelize/sequelize/issues"
    },
    "contributors": [
        {
            "name": "Sascha Depold"
        },
        {
            "name": "Jan Aagaard Meier"
        },
        {
            "name": "Daniel Durante"
        },
        {
            "name": "Mick Hansen"
        }
    ],
    "dependencies": {
        "bluebird": "^3.3.4",
        "depd": "^1.1.0",
        "dottie": "^1.0.0",
        "generic-pool": "2.4.2",
        "inflection": "^1.6.0",
        "lodash": "4.12.0",
        "moment": "^2.13.0",
        "moment-timezone": "^0.5.4",
        "retry-as-promised": "^2.0.0",
        "semver": "^5.0.1",
        "shimmer": "1.1.0",
        "terraformer-wkt-parser": "^1.1.0",
        "toposort-class": "^1.0.1",
        "uuid": "^3.0.0",
        "validator": "^5.2.0",
        "wkx": "0.2.0"
    },
    "description": "Multi dialect ORM for Node.JS/io.js",
    "devDependencies": {
        "chai": "^3.5.0",
        "chai-as-promised": "^5.1.0",
        "chai-datetime": "^1.4.0",
        "chai-spies": "^0.7.0",
        "commander": "^2.6.0",
        "continuation-local-storage": "^3.1.4",
        "cross-env": "^2.0.1",
        "dox": "~0.8.0",
        "git": "^0.1.5",
        "hints": "^0.2.0",
        "istanbul": "^0.4.3",
        "jshint": "^2.9.2",
        "lcov-result-merger": "^1.2.0",
        "mocha": "^2.4.2",
        "mysql": "~2.10.1",
        "pg": "^4.4.6",
        "pg-hstore": "^2.3.1",
        "pg-native": "^1.8.0",
        "pg-types": "^1.11.0",
        "rimraf": "^2.5.4",
        "sinon": "^1.17.4",
        "sinon-chai": "^2.8.0",
        "sqlite3": "^3.1.4",
        "tedious": "^1.13.2",
        "uuid-validate": "^0.0.2",
        "watchr": "~2.4.11"
    },
    "directories": {},
    "dist": {
        "shasum": "bda2df1e31854b099e4149a111e9fc0a5ca1d1a4",
        "tarball": "https://registry.npmjs.org/sequelize/-/sequelize-3.30.4.tgz"
    },
    "engines": {
        "node": ">=0.6.21"
    },
    "gitHead": "0d1a558ae182062d264eecd3cdfa1e962b06fb8c",
    "homepage": "https://github.com/sequelize/sequelize#readme",
    "keywords": [
        "mysql",
        "sqlite",
        "postgresql",
        "postgres",
        "mssql",
        "orm",
        "nodejs",
        "object relational mapper"
    ],
    "license": "MIT",
    "main": "index",
    "maintainers": [
        {
            "name": "sdepold"
        },
        {
            "name": "durango"
        },
        {
            "name": "mickhansen"
        },
        {
            "name": "janaameier"
        }
    ],
    "name": "sequelize",
    "optionalDependencies": {},
    "repository": {
        "type": "git",
        "url": "git+https://github.com/sequelize/sequelize.git"
    },
    "scripts": {
        "build-docker": "docker-compose build",
        "cover": "rimraf coverage && npm run teaser && npm run cover-unit && npm run cover-integration && npm run merge-coverage",
        "cover-integration": "cross-env COVERAGE=true node_modules/.bin/istanbul cover ./node_modules/mocha/bin/_mocha --report lcovonly -- -t 60000 --ui tdd \"test/integration/**/*.test.js\" && node -e \"require('fs').renameSync('coverage/lcov.info', 'coverage/integration.info')\"",
        "cover-unit": "cross-env COVERAGE=true node_modules/.bin/istanbul cover ./node_modules/mocha/bin/_mocha --report lcovonly -- -t 30000 --ui tdd \"test/unit/**/*.test.js\" && node -e \"require('fs').renameSync('coverage/lcov.info', 'coverage/unit.info')\"",
        "docs": "node docs/docs-generator.js",
        "jshint": "jshint lib test",
        "merge-coverage": "lcov-result-merger \"coverage/*.info\" \"coverage/lcov.info\"",
        "sscce": "docker-compose run sequelize /bin/sh -c \"node sscce.js\"",
        "sscce-mysql": "cross-env DIALECT=mysql npm run sscce",
        "sscce-postgres": "cross-env DIALECT=postgres npm run sscce",
        "sscce-sqlite": "cross-env DIALECT=sqlite npm run sscce",
        "teaser": "echo ''; node -pe \"Array(20 + process.env.DIALECT.length + 3).join('#')\"; echo '# Running tests for '$DIALECT' #'; node -pe \"Array(20 + process.env.DIALECT.length + 3).join('#')\";echo '';",
        "test": "npm run jshint && npm run teaser && npm run test-unit && npm run test-integration",
        "test-all": "npm run test-mysql && npm run test-sqlite && npm run test-postgres && npm run test-postgres-native && npm run test-mariadb && npm run test-mssql",
        "test-docker": "docker-compose run sequelize /bin/sh -c \"npm run test-all\"",
        "test-docker-integration": "docker-compose run sequelize /bin/sh -c \"npm run test-integration-all\"",
        "test-docker-unit": "docker-compose run sequelize /bin/sh -c \"npm run test-unit-all\"",
        "test-integration": "mocha --globals setImmediate,clearImmediate --ui tdd --check-leaks --colors -t 30000 --reporter spec \"test/integration/**/*.test.js\"",
        "test-integration-all": "npm run test-integration-mysql && npm run test-integration-postgres && npm run test-integration-postgres-native && npm run test-integration-mssql && npm run test-integration-sqlite && npm run test-integration-mariadb",
        "test-integration-mariadb": "cross-env DIALECT=mariadb npm run test-integration",
        "test-integration-mssql": "cross-env DIALECT=mssql npm run test-integration",
        "test-integration-mysql": "cross-env DIALECT=mysql npm run test-integration",
        "test-integration-postgres": "cross-env DIALECT=postgres npm run test-integration",
        "test-integration-postgres-native": "cross-env DIALECT=postgres-native npm run test-integration",
        "test-integration-sqlite": "cross-env DIALECT=sqlite npm run test-integration",
        "test-mariadb": "cross-env DIALECT=mariadb npm test",
        "test-mssql": "cross-env DIALECT=mssql npm test",
        "test-mysql": "cross-env DIALECT=mysql npm test",
        "test-pgsql": "npm run test-postgres",
        "test-postgres": "cross-env DIALECT=postgres npm test",
        "test-postgres-native": "cross-env DIALECT=postgres-native npm test",
        "test-postgresn": "npm run test-postgres-native",
        "test-sqlite": "cross-env DIALECT=sqlite npm test",
        "test-unit": "mocha --globals setImmediate,clearImmediate --ui tdd --check-leaks --colors -t 30000 --reporter spec \"test/unit/**/*.js\"",
        "test-unit-all": "npm run test-unit-mysql && npm run test-unit-postgres && npm run test-unit-postgres-native && npm run test-unit-mssql && npm run test-unit-sqlite && npm run test-unit-mariadb",
        "test-unit-mariadb": "cross-env DIALECT=mariadb npm run test-unit",
        "test-unit-mssql": "cross-env DIALECT=mssql npm run test-unit",
        "test-unit-mysql": "cross-env DIALECT=mysql npm run test-unit",
        "test-unit-postgres": "cross-env DIALECT=postgres npm run test-unit",
        "test-unit-postgres-native": "cross-env DIALECT=postgres-native npm run test-unit",
        "test-unit-sqlite": "cross-env DIALECT=sqlite npm run test-unit"
    },
    "version": "3.30.4"
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
