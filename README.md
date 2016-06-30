# Clone

This module clones a Javascript object in safe mode (eg: drops circular values) recursively. Circular values are replaced with a string: `'[Circular]'`.

Ideas from [tracker1/safe-clone-deep](https://github.com/tracker1/safe-clone-deep). I improved the workflow a bit by:
- refactoring the code (complete rewrite)
- fixing node 6+
- minor performance tweaks
- use of `Array.isArray` and `Buffer.isBuffer`

## Installation

```
npm install @soyuka/clone
```

## Usage

```
const clone = require('@soyuka/clone')

let a = {b: a, c: 'hello'}
let o = clone(a)

console.log(o)
// outputs: { c: 'hello', b: '[Circular]' }
```

## TODO

Browser usage