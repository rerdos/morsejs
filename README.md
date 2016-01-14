# morsejs

[![Build Status](https://travis-ci.org/zero298/morsejs.svg?branch=master)](https://travis-ci.org/zero298/morsejs) [![Inline docs](http://inch-ci.org/github/zero298/morsejs.svg?branch=master)](http://inch-ci.org/github/zero298/morsejs)

A morse code translation library written in JavaScript

[Working implementation of morsejs](http://zero298.github.io/morsejs/)

## Translation

**morsejs:translate** will translate a given String to an Array of Numbers found in the signal enumeration (by default: `0`,`1`).

The return structure is formated so that it is similar to the transmission format of a morse message.  This means that it includes the spacing between symbol signals, the symbols themselves, and words.  See [transmission of morse code on Wikipedia](https://en.wikipedia.org/wiki/Morse_code#Transmission) for a better explanation.

By default, this library transmits `0` for any padding between signals, symbols, or words.  Similarly, it sends `0` for a short signal and 3 `0` for a long signal.

Consider the transmission of "SOS":
```
         1         2         3
123456789012345678901234567890
-_-_-___---_---_---___-_-_-
```

**morsejs** would actually return:

```
[ 1, 0, 1, 0, 1, 0, 0, 0, 1, 1, 1, 0, 1, 1, 1, 0, 1, 1, 1, 0, 0, 0, 1, 0, 1, 0, 1, 0]
```

Note: there is plus 0 in the end

## Installation

### Binary

```bash
npm install -g morsejs
```

### Dependency

```bash
npm install --save morsejs
```

## Usage

### CLI

```bash
morsejs hello world
```

### JS

If you just want to plainly translate a message, you can just use **translate**
```javascript
var message = morsejs.translate("hello world");
```

All the other plugins won't work.
