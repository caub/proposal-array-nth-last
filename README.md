# Getting nth-last item from an array

## Rationale

Currently the only ways to get an element from the end of an Array is with the `.length` property:`someArray[someArray.length - n]` or using the `.slice` method: `someArray.slice(-1)[0]`

## High Level Proposal

We propose to add the `Symbol.index` protocol to `Array`

```js
Array.prototype[Symbol.index](n, fromEnd = false) { }
```

The existing `someArray[n]` desugars to`someArray[Symbol.index](n)`

The new proposed syntax `someArray[^n]` desugars to `someArray[Symbol.index](n, true)`

This protocol could be added to `String` as well

## Specification

// TODO

## Related proposal

Compared to https://github.com/keithamus/proposal-array-last, the benefit in our proposal is to:

- avoid any web-compatibility issue
- avoid "magic" getters
- have a more powerful and user-friendly syntax, similarly to https://github.com/tc39/proposal-slice-notation
