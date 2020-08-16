# rrrange

create range objects and work with sets theory (inclusion, overlapping, union and so on)

## import

works with browser (ES6+) and Nodejs

in browser, include the rrrange.js file

in node :

```js
const rrrange = require('rrrange')
```

## use

rrrange let you create range objects, storing only the boundaries.
You can then do a selection of operations, such as

- test if some value is in the range
- test if the range overlaps another range,
- get the union of 2 ranges
- ...
- create arrays from range by specifying a step

by default ranges includes boundaries

```js
const range = rrrange(2,8)
const range2 = new rrrange.Range(2,8) // similar

range.includes(5.2) // true
range.includes(0) // false

range.overlaps(rrrange(4,6)) // true

range.intersects(rrrange(-2,5)) // true

range.reverse() // returns Range(8,2)

range.excludeStart() // returns an open range on 2

range.by(2) // [2,4,6,8]
range.excludeStart().exludeEnd().by(2) // [4,6]
```
