# hugo-lunr
## Generate lunr.js index files from Hugo static sites
A simple way to add site search to your static [Hugo](https://gohugo.io/) site using [Lunr.js](http://lunrjs.com/). Hugo-lunr will create an index file of any html and markdown documents in your Hugo project, only non-draft documents get added to the index.

## Options
By default hugo-lunr will read the `content` directory of your Hugo project and output the lunr index to `public/lunr.json`. If you are using the command line implementation you can pass an input directory `-i` and and output path/file `-o`.

## How to use hugo-lunr CLI
The easiest way to use hugo-lunr is via npm scripts:
```
  "scripts": {
    "index": "node ./node_modules/bin/index.js"
  },
```

or to pass arguments for input and output:

```
  "scripts": {
    "index": "node ./node_modules/bin/index.js -i \"content/subdir/**\" -o public/my-index.json"
  },
```

Which can be executed from a terminal prompt
```
$ npm run index
```

## How to use hugo-lunr API
```javascript
var hugolunr = require('hugo-lunr');
new hugolunr().index();
```

or to set input/output paths

```javascript
var hugolunr = require('hugo-lunr');
var h = new hugolunr();
h.setInput('content/faq/**');
h.setOutput('public/faq.json');
h.index();
```

## How to use Lunr.jr
Checkout this [example page](http://lunrjs.com/example/) to see how to setup search using lunr.js on your website.
