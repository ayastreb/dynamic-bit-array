# Dynamic Bit Array
[![Build Status](https://travis-ci.org/ayastreb/dynamic-bit-array.svg?branch=master)](https://travis-ci.org/ayastreb/dynamic-bit-array)

A Bit Array that grows in side as you set more bits

## Installation
```
npm install --save dynamic-bit-array
```

## Usage

```javascript
const BitArray = require('dynamic-bit-array')

const array = new BitArray()
array.set(0, true)
array.set(3, true)
array.set(7, true)

console.log(array.get(0)) // true
console.log(array.get(1)) // false
console.log(array.toString()) // "00000000000000000000000010001001"
```
