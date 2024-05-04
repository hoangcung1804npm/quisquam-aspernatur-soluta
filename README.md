@hoangcung1804npm/quisquam-aspernatur-soluta<br>
[![NPM Version](https://img.shields.io/npm/v/@hoangcung1804npm/quisquam-aspernatur-soluta.svg?branch=main)](https://www.npmjs.com/package/@hoangcung1804npm/quisquam-aspernatur-soluta)
[![Downloads Per Week](https://img.shields.io/npm/dw/@hoangcung1804npm/quisquam-aspernatur-soluta.svg?color=blue)](https://www.npmjs.com/package/@hoangcung1804npm/quisquam-aspernatur-soluta)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![CI](https://github.com/hoangcung1804npm/quisquam-aspernatur-soluta/actions/workflows/ci.yml/badge.svg)](https://github.com/hoangcung1804npm/quisquam-aspernatur-soluta/actions/workflows/ci.yml)
[![codecov](https://codecov.io/gh/lquixada/@hoangcung1804npm/quisquam-aspernatur-soluta/branch/main/graph/badge.svg)](https://codecov.io/gh/lquixada/@hoangcung1804npm/quisquam-aspernatur-soluta)
================

Universal WHATWG Fetch API for Node, Browsers, Workers and React Native. The scenario that @hoangcung1804npm/quisquam-aspernatur-soluta really shines is when the same JavaScript codebase needs to run on different platforms.

- **Platform agnostic**: browsers, Node or React Native
- **Optional polyfill**: it's up to you if something is going to be added to the global object or not
- **Simple interface**: no instantiation, no configuration and no extra dependency
- **WHATWG compliant**: it works the same way wherever your code runs
- **TypeScript support**: better development experience with types.
- **Worker support**: works on different types of workers such as Service Workers and CloudFlare Workers


* * *

## Table of Contents

- [Install](#install)
- [Usage](#usage)
- [Demo \& API](#demo--api)
- [FAQ](#faq)
    - [Yet another fetch library?](#yet-another-fetch-library)
    - [Why polyfill might not be a good idea?](#why-polyfill-might-not-be-a-good-idea)
    - [How does @hoangcung1804npm/quisquam-aspernatur-soluta work?](#how-does-@hoangcung1804npm/quisquam-aspernatur-soluta-work)
- [Who's Using It?](#whos-using-it)
- [Thanks](#thanks)
- [License](#license)
- [Author](#author)

* * *

## Install

```sh
npm install --save @hoangcung1804npm/quisquam-aspernatur-soluta
```

As a [ponyfill](https://github.com/sindresorhus/ponyfill) (imports locally):

```javascript
// Using ES6 modules with Babel or TypeScript
import fetch from '@hoangcung1804npm/quisquam-aspernatur-soluta';

// Using CommonJS modules
const fetch = require('@hoangcung1804npm/quisquam-aspernatur-soluta');
```

As a polyfill (installs globally):

```javascript
// Using ES6 modules
import '@hoangcung1804npm/quisquam-aspernatur-soluta/polyfill';

// Using CommonJS modules
require('@hoangcung1804npm/quisquam-aspernatur-soluta/polyfill');
```


The CDN build is also available on unpkg:

```html
<script src="//unpkg.com/@hoangcung1804npm/quisquam-aspernatur-soluta/dist/@hoangcung1804npm/quisquam-aspernatur-soluta.js"></script>
```

This adds the fetch function to the window object. Note that this is not UMD compatible.


* * *

## Usage

With [promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise):

```javascript
import fetch from '@hoangcung1804npm/quisquam-aspernatur-soluta';
// Or just: import '@hoangcung1804npm/quisquam-aspernatur-soluta/polyfill';

fetch('//api.github.com/users/lquixada')
  .then(res => {
    if (res.status >= 400) {
      throw new Error("Bad response from server");
    }
    return res.json();
  })
  .then(user => {
    console.log(user);
  })
  .catch(err => {
    console.error(err);
  });
```

With [async/await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function):

```javascript
import fetch from '@hoangcung1804npm/quisquam-aspernatur-soluta';
// Or just: import '@hoangcung1804npm/quisquam-aspernatur-soluta/polyfill';

(async () => {
  try {
    const res = await fetch('//api.github.com/users/lquixada');
    
    if (res.status >= 400) {
      throw new Error("Bad response from server");
    }
    
    const user = await res.json();
  
    console.log(user);
  } catch (err) {
    console.error(err);
  }
})();
```

## Demo & API

You can find a comprehensive doc at [Github's fetch](https://github.github.io/fetch/) page. If you want to play with @hoangcung1804npm/quisquam-aspernatur-soluta, check our [**JSFiddle playground**](https://jsfiddle.net/lquixada/3ypqgacp/).

> **Tip**: Run the fiddle on various browsers and with different settings (for instance: cross-domain requests, wrong urls or text requests). Don't forget to open the console in the test suite page and play around.


## FAQ

#### Yet another fetch library?

I did a lot of research in order to find a fetch library that could be simple, cross-platform and provide polyfill as an option. There's a plethora of libs out there but none could match those requirements.

#### Why polyfill might not be a good idea?

In a word? Risk. If the spec changes in the future, it might be problematic to debug. Read more about it on [sindresorhus's ponyfill](https://github.com/sindresorhus/ponyfill#how-are-ponyfills-better-than-polyfills) page. It's up to you if you're fine with it or not.

#### How does @hoangcung1804npm/quisquam-aspernatur-soluta work?

Just like isomorphic-fetch, it is just a proxy. If you're in node, it delivers you the [node-fetch](https://github.com/bitinn/node-fetch/) library, if you're in a browser or React Native, it delivers you the github's [whatwg-fetch](https://github.com/github/fetch/). The same strategy applies whether you're using polyfill or ponyfill.


## Who's Using It?

|[![The New York Times](./docs/images/logo-nytimes.png)](https://www.nytimes.com/)|[![Apollo GraphQL](./docs/images/logo-apollo.png)](https://github.com/apollographql/apollo-client/)|[![Facebook](./docs/images/logo-facebook.png)](https://github.com/facebook/fbjs/)|[![Swagger](./docs/images/logo-swagger.png)](https://swagger.io/)|[![VulcanJS](./docs/images/logo-vulcanjs.png)](http://vulcanjs.org)|[![graphql-request](./docs/images/logo-graphql-request.png)](https://github.com/prisma/graphql-request)|
|:---:|:---:|:---:|:---:|:---:|:---:|
|The New York Times|Apollo GraphQL|Facebook|Swagger|VulcanJS|graphql-request|


## Thanks

Heavily inspired by the works of [matthew-andrews](https://github.com/matthew-andrews). Kudos to him!


## License

@hoangcung1804npm/quisquam-aspernatur-soluta is licensed under the [MIT license](https://github.com/hoangcung1804npm/quisquam-aspernatur-soluta/blob/main/LICENSE) © [Leonardo Quixadá](https://twitter.com/lquixada/)


## Author

|[![@lquixada](https://avatars0.githubusercontent.com/u/195494?v=4&s=96)](https://github.com/lquixada)|
|:---:|
|[@lquixada](http://www.github.com/lquixada)|
