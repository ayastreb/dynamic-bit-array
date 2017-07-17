# Dynamic Bit Array
[![Build Status](https://travis-ci.org/ayastreb/dynamic-bit-array.svg?branch=master)](https://travis-ci.org/ayastreb/dynamic-bit-array)

A Bit Array that grows in side as you set more bits

## Installation
```
npm install --save dynamic-bit-array
```

## Usage

### Setting and checking bits

```javascript
const BitArray = require('dynamic-bit-array')

const array = new BitArray()
array.set(0, true)
array.set(3, true)
array.set(7, true)

console.log(array.get(0)) // true
console.log(array.get(1)) // false
console.log(array.toString()) // "00000000000000000000000010001001"
console.log(array.toString(/*skipLeadingZero=*/true)) // "10001001"
```

### Creating bit array from string

```javascript
const BitArray = require('dynamic-bit-array')

const array = BitArray.fromString("1001")

console.log(array.get(0)) //true
console.log(array.get(1)) //false
console.log(array.get(2)) //false
console.log(array.get(3)) //true
console.log(array.toString(/*skipLeadingZero=*/true)) // "1001"
```

### Logical operations on arrays

### NOT
```javascript
const BitArray = require('dynamic-bit-array')

const array = new BitArray(32)
console.log(array.toString()) // "00000000000000000000000000000000"
console.log(array.not().toString()) // "11111111111111111111111111111111"

const other = BitArray.fromString("00000000000000001111111111111111")
console.log(other.not().toString()) // "11111111111111110000000000000000"
```

### AND
```javascript
const BitArray = require('dynamic-bit-array')

const arrayA = BitArray.fromString("1001")
const arrayB = BitArray.fromString("1100")

console.log(arrayA.and(arrayB).toString(/*skipLeadingZero=*/true)) // "1000"
```

### OR
```javascript
const BitArray = require('dynamic-bit-array')

const arrayA = BitArray.fromString("1001")
const arrayB = BitArray.fromString("1100")

console.log(arrayA.or(arrayB).toString(/*skipLeadingZero=*/true)) // "1101"
```

### XOR
```javascript
const BitArray = require('dynamic-bit-array')

const arrayA = BitArray.fromString("1001")
const arrayB = BitArray.fromString("1100")

console.log(arrayA.xor(arrayB).toString(/*skipLeadingZero=*/true)) // "0101"
```
