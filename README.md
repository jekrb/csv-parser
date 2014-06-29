# csv-parser

Streaming csv parser inspired by binary-csv that aims to be faster than everyone else

```
npm install csv-parser
```

[![build status](http://img.shields.io/travis/mafintosh/csv-parser.svg?style=flat)](http://travis-ci.org/mafintosh/csv-parser)
![dat](http://img.shields.io/badge/Development%20sponsored%20by-dat-green.svg?style=flat)

## Usage

Simply instantiate `csv` and pump a csv file to it and get the rows out as objects

``` js
var csv = require('csv-parser')

fs.createReadStream('some-csv-file.csv')
  .pipe(csv())
  .on('data', function(data) {
    console.log('row', data)
  })
```

The data emitted is a normalized JSON object

The csv constructor accepts the following options as well

``` js
var stream = csv({
  raw: false,    // do not decode to utf-8 strings
  separator: ',' // specify optional cell separator
})
```

## License

MIT
