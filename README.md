# wgrep
> Web grep: search all rendered resources used by a URI

[![Coverage][cov-image]][cov-url]
[![Tests][test-image]][test-url]
[![Dependencies][deps-image]][deps-url]
[![Badge Fury][fury-image]][fury-url]
[![Inline docs][inch-image]][inch-url]

This `node` command-line utility uses a headless browser (Puppeteer) to render
a webpage and download all resources it may need. These resources including the
original HTML are all saved locally which it searches one-by-one for a text
string.

*Since we are downloading all resources it is easy to determine the total
download size.*

## Features

* Search using regular expressions
* A screen capture is created (not configurable)

## Installation

	$ git clone https://github.com/stav/wgrep.git
	$ cd wgrep
	$ npm install -g

## Usage example

Let's try to find the string "stav" from the repository website on GitHub:

	$ wgrep stav https://github.com/stav/wgrep

	Calling for "stav" in "output" from "https://github.com/stav/wgrep" with user "undefined"
	Looking in "output" for 'stav'
	Found 1 files
	[ 'output/stav/wgrep/index.html' ]

It was only found in the `index.html` page.

Now let's see what the total download size was:

	$ du -sh output
	1.4M    output

## Options

	$ wgrep --help

	Usage: wgrep [options] <regex> <url>

	Options:
	  -d, --directory <directory>  The output directory (default: "output")
	  -u, --username <username>    The user to authenticate as
	  -h, --help                   output usage information

## Tests

	$ npm test

	$ npm run test-e2e

## Contributing

Please file any issues you have.

If you fix a bug or add new features it would be great to have you fork this
repo and submit a pull request:

1. Fork it (`https://github.com/yourname/yourproject/fork`)
2. Create your feature branch (`git checkout -b feature/fooBar`)
3. Commit your changes (`git commit -am 'Add some fooBar'`)
4. Push to the branch (`git push origin feature/fooBar`)
5. Create a new Pull Request

## Status

* https://david-dm.org/stav/wgrep
* https://inch-ci.org/github/stav/wgrep?branch=master   ????
* https://badge.fury.io/for/gh/stav/wgrep

## License

Apache 2.0

<!-- Markdown link & img dfn's -->
[test-image]: https://github.com/stav/wgrep/workflows/tests/badge.svg
[test-url]:   https://github.com/stav/wgrep/workflows
[fury-image]: https://badge.fury.io/for/gh/stav%2Fwgrep.svg
[fury-url]:   https://badge.fury.io/for/gh/stav%2Fwgrep
[inch-image]: http://inch-ci.org/github/stav/wgrep.svg?branch=master
[inch-url]:   http://inch-ci.org/github/stav/wgrep
[deps-image]: https://david-dm.org/stav/wgrep/status.svg
[deps-url]:   https://david-dm.org/stav/wgrep
[cov-image]:  https://codecov.io/gh/stav/wgrep/branch/master/graph/badge.svg
[cov-url]:    https://codecov.io/github/stav/wgrep
