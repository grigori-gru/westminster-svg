# westminster-svg

Generate westminster parliament charts as **[virtual-dom](https://github.com/Matt-Esch/virtual-dom#virtual-dom) SVG**. Design inspired by the [Wikipedia parliament charts](https://github.com/slashme/parliamentdiagram). *Play around with the [__live demo__](https://juliuste.github.io/westminster-svg/)!* For "normal" parliament charts, see [parliament-svg](https://github.com/juliuste/parliament-svg).

[![npm version](https://img.shields.io/npm/v/westminster-svg.svg)](https://www.npmjs.com/package/westminster-svg)
[![dependency status](https://img.shields.io/david/juliuste/westminster-svg.svg)](https://david-dm.org/juliuste/westminster-svg)
[![dev dependency status](https://img.shields.io/david/dev/juliuste/westminster-svg.svg)](https://david-dm.org/juliuste/westminster-svg#info=devDependencies)
[![license](https://img.shields.io/github/license/juliuste/westminster-svg.svg?style=flat)](LICENSE)
[![chat on gitter](https://badges.gitter.im/juliuste.svg)](https://gitter.im/juliuste)

## Installation

```shell
npm install --save westminster-svg
```

## Usage

```js
const westminsterSVG = require('westminster-svg')

const svg = westminsterSVG(parliament)
```

`parliament` is an object containing party information for all four 'sides' of the parliament: `headBench`, `left`, `crossBench` and `right`. After the [UK general election 2017](https://en.wikipedia.org/wiki/United_Kingdom_general_election,_2017) it should look as follows:

```js
{
	headBench: {
		speaker: {
			seats: 1,
			colour: '#000'
		}
	},
	left: {
		labour: {
			seats: 262,
			colour: '#dc241f',
		},
		snp: {
			seats: 35,
			colour: '#ff0',
		},
		libdems: {
			seats: 12,
			colour: '#faa61a',
		},
		sinnfein: {
			seats: 7,
			colour: '#080',
		},
		plaidcymru: {
			seats: 4,
			colour: '#008142',
		},
		green: {
			seats: 1,
			colour: '#6ab023',
		},
		independent: {
			seats: 1,
			colour: '#aadfff',
		}
	},
	crossBench: {
		dup: {
			seats: 10,
			colour: '#d46a4c',
		}
	},
	right: {
		conservative: {
			seats: 317,
			colour: '#0087dc',
		}
	}
}
```

Please note that the parties will be displayed in the order of their `object` keys from left to right (based on the speaker's viewpoint). Further, each seat SVG element contains the party name in its `class` attribute.

For the given `parliament` object, the rendered result should look like this:

![Example: House of Commons after GE 2017](https://rawgit.com/juliuste/westminster-svg/master/example/westminster.svg)

If you want to convert the virtual DOM tree to HTML/SVG string, use `virtual-dom-stringify`:

```js
const toStr = require('virtual-dom-stringify')

const svg = toStr(westminsterSVG(parliament))
```

## Contributing

If you found a bug, want to propose a feature or feel the urge to complain about your life, feel free to visit [the issues page](https://github.com/juliuste/westminster-svg/issues).
