# You don't need

Session by Brigitte Jellinek [bjelline](https://github.com/bjelline)

*JavaScript has improved. Many New  language features were added over the years.*

*New tools were built. The workflow for frontend projects has changed and become more complex....*

*Will we only add new stuff, or is it time to drop some old stuff? Old habits, old patters, old tools that we no longer need.  Can we simplify the workflow again?*


* JavaScript the Language
* Tools
* Browser APIs



## JavaScript the Language

### you don't need closures or immediadelty invoced functions

In JavaScript everything used to be public and dynamic.

We used closures [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures) to keep stuff constant.

```
function makeProtectedName(name) {
  function getName() {
    console.log(name);
    return name;
  }
  return getName;
}

const getPassword = makeProtectedName("Secret Name");
getPassword();

const getKey = makeProtectedName("234oiasfas908wjafsd");
getKey();
```
We now have const and private properties:

```
const password = "Secret Name";
const key = "234oiasfas908wjafsd";
```


### you don't need closures or immediadelty invoced functions

We used closures and immediately invoced functions - IIF [MDN](https://developer.mozilla.org/en-US/docs/Glossary/IIFE) to get private properties and private methods:

[demo](./example-iif.html)


we now have classes with private properties and even private methods

[demo](./example-private.html)


### you don't need callbacks, you often don't need promise.then

use `async` and `await`.

you will still need Promise.all(), and you will need to understand them.

WARNING: if you code directly in the developer tools, in the console,  async await does not work in all cases.


### you may not need promise.catch in every case

you can use try ... catch ... finally to catch several possible exceptions


## Tools

* use bun or deno instead of node.js, then you don't need a compile step
* use [JSDOC commets as type-annotations](https://www.typescriptlang.org/docs/handbook/jsdoc-supported-types.html), and you can just run JavaScript directly
    * use [ts-to-jsdoc](https://www.npmjs.com/package/ts-to-jsdoc) to convert old typescript to this
* you don't need lodash - https://github.com/you-dont-need/You-Dont-Need-Lodash-Underscore?tab=readme-ov-file
* instead of nginx+certbot use [caddy](https://caddyserver.com/)
* instead of nvm + rvm + .... use [mise](https://mise.jdx.dev/) to handle all your node versions, ruby versions, python versions, ...


### you don't need a bundler

the bundler was invented in a time without proper modules and to concatenate many files into one to improve http performance.

with http2 and http3 loading several files instead of one does not add loading time.

with importmaps [MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script/type/importmap) your source code can just import bare modules, and specify from where you a loading in a separate importmap.

HTTP3: supported by cadyy,


## Browser APIs

* [FinalizationRegistry](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/FinalizationRegistry) helps you react to objects being garbage collected
* [AbortController](https://developer.mozilla.org/en-US/docs/Web/API/AbortController/abort) helps with aborting fetches


## you still need ....

* terribly HTML and CSS for e-mails [caniemail](https://www.caniemail.com/)
