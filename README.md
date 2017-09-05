[![npm version](https://badge.fury.io/js/bacon.atom.svg)](http://badge.fury.io/js/bacon.atom)
[![Build Status](https://travis-ci.org/calmm-js/bacon.atom.svg?branch=master)](https://travis-ci.org/calmm-js/bacon.atom)
[![Code Coverage](https://img.shields.io/codecov/c/github/calmm-js/bacon.atom/master.svg)](https://codecov.io/github/calmm-js/bacon.atom?branch=master)
[![](https://david-dm.org/calmm-js/bacon.atom.svg)](https://david-dm.org/calmm-js/bacon.atom)
[![](https://david-dm.org/calmm-js/bacon.atom/dev-status.svg)](https://david-dm.org/calmm-js/bacon.atom?type=dev)

A garbage collectable alternative to
[Bacon.Model](https://github.com/baconjs/bacon.model).

## Reference

```js
import Atom from "bacon.atom"
```

### Atom(initialValue)

Creates a new atom with the given initial value.  An atom is a modifiable
Bacon [property](https://github.com/baconjs/bacon.js#property).  Atoms (and
lensed atoms) implicitly skip duplicates using an acyclic structural equality
predicate.

### atom.get()

A slow operation to synchronously get the current value of the atom.  Use of
`get` is discouraged: prefer to depend on an atom as you would with ordinary
Bacon properties.

### atom.view(lens)

Creates a new lensed atom with the [partial
lens](https://github.com/calmm-js/partial.lenses/) from the original atom.
Modifications to the lensed atom are reflected in the original atom and vice
versa.

### atom.modify(currentValue => newValue)

Applies the given function to the current value of the atom and replaces the
value of the atom with the new value returned by the function.

### atom.set(value)

`atom.set(value)` is equivalent to `atom.modify(() => value)` and is provided
for convenience.
