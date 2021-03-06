# Quality assurance (QA) 

Quality assurance (`binaries`) for your PHP projects

-----

[![Build Status](https://img.shields.io/travis/fiolasoft/qa.svg?style=flat-square)](https://travis-ci.org/fiolasoft/qa)
[![Downloads total](https://img.shields.io/packagist/dt/fiolasoft/qa.svg?style=flat-square)](https://packagist.org/packages/fiolasoft/qa)
[![Latest stable](https://img.shields.io/packagist/v/fiolasoft/qa.svg?style=flat-square)](https://packagist.org/packages/fiolasoft/qa)

## Install

```bash
composer require --dev fiolasoft/qa
```

## Manual usage (bin)

### CodeSniffer & CodeFixer

Default folders are: `src`, `app`, `tests`
Default extensions are: `php`, `php3`, `php4`, `php5`, `phtml`, `phpt`
Default excluded folders are: `*/temp`, `*/tmp`

By default is used `ruleset.xml` in library/project root of your project. Otherwise, strict default one is used.

```sh
vendor/bin/codesniffer
vendor/bin/codesniffer <folder1> <folder2>
```

```sh
vendor/bin/codefixer
vendor/bin/codefixer <folder1> <folder2>
```

### Linter (PHP)

Default folders are: `src`, `app`, `tests`

```sh
vendor/bin/linter
vendor/bin/linter <folder1> <folder2>
```

### Executing

```
composer qa
composer run qa
composer run-script qa
```

### Composer

```json
{
  "scripts": {
    "qa": [
      "linter src tests",
      "codesniffer src tests"
    ],
    "tester": [
      "tester -s -p php --colors 1 -c tests/php-unix.ini tests/cases"
    ],
    "tester-coverage": [
      "tester -s -p php --colors 1 -c tests/php-unix.ini -d extension=xdebug.so --coverage ./coverage.xml --coverage-src ./src tests/cases "
    ]
  }
}
```

-----

Thanks for testing, reporting and contributing.
