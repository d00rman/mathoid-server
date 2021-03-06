# Mathoid-server

[![Build Status][1]][2] [![dependency status][3]][4] [![dev dependency status][5]][6] [![Coverage Status][7]][8]

[![NPM][9]][10]

Mathoid-server is a service that uses MathJax and PhantomJS to create SVGs and MathML on server side.
Mathoid-server is a based on svgtex - https://github.com/agrbin/svgtex.



## Installation
see http://formulasearchengine.com/mathoid


## API Description

There is basically just one entry point '/' with one required POST parameter 'q'.

#### q (input to be converted)

* required parameter
* no $ for (La)TeX input

#### type (the input type)
* optional
* defalult 'tex'
* possible values
  * tex (texvc input will be verified by texvccheck)
  * mml (MathML input, used in MW_MATH_LATEXML rendering mode)
  * ascii (ascii mathml input, experimental)

## Create a new release

Checkout the latest version and switch to the master branch:
* git-dch -R -N version
* git-buildpackage --git-tag -S

see also https://wikitech.wikimedia.org/wiki/Git-buildpackage

publish as ppa
* dput ppa:physikerwelt/mathoid ../version.changes



## Tests
Based on the Template for creating MediaWiki Services in Node.js
The template also includes a test suite a small set of executable tests. To fire
them up, simply run:

```
npm test
```

If you haven't changed anything in the code (and you have a working Internet
connection), you should see all the tests passing. As testing most of the code
is an important aspect of service development, there is also a bundled tool
reporting the percentage of code covered. Start it with:

```
npm run-script coverage
```

### Troubleshooting

In a lot of cases when there is an issue with node it helps to recreate the
`node_modules` directory:

```
rm -r node_modules
npm install
```

[1]: https://travis-ci.org/physikerwelt/mathoid-server.svg
[2]: https://travis-ci.org/physikerwelt/mathoid-server
[3]: https://david-dm.org/physikerwelt/mathoid-server.svg
[4]: https://david-dm.org/physikerwelt/mathoid-server
[5]: https://david-dm.org/physikerwelt/mathoid-server/dev-status.svg
[6]: https://david-dm.org/physikerwelt/mathoid-server#info=devDependencies
[7]: https://img.shields.io/coveralls/physikerwelt/mathoid-server.svg
[8]: https://coveralls.io/r/physikerwelt/mathoid-server
[9]: https//nodei.co/npm/mathoid.svg
[10]: https://nodei.co/npm/mathoid/
