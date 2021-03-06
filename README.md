# safe-trim
---

[![Build Status](https://travis-ci.org/aligay/safe-trim.svg?branch=master)](https://travis-ci.org/aligay/safe-trim/branches)
[![codecov](https://codecov.io/gh/aligay/safe-trim/branch/master/graph/badge.svg)](https://codecov.io/gh/aligay/safe-trim)
[![dependencies Status](https://david-dm.org/aligay/safe-trim/status.svg)](https://david-dm.org/aligay/safe-trim)
[![devDependencies Status](https://david-dm.org/aligay/safe-trim/dev-status.svg)](https://david-dm.org/aligay/safe-trim?type=dev)

## install
```
npm install safe-trim
```
## use
```
import safeTrim from 'safe-trim'
safeTrim('    a      b  ')
```

## remove Invisible spaces

```
let str = '  "a":1    a \r\n\r\t  ᠎             　b       '
let ret = safeTrim(str)
expect(ret).toEqual('"a":1    a\n\nb')
```

## convert CR CR-LR into LR
```
a\r\n\r\nb  => 'a\n\nb'
a\r\rb => 'a\n\nb'
a\r\r\nb => 'a\n\nb'
```

## remove BOM
```
JSON.parse('﻿{"a":1}') // ❗️Error because BOM

JSON.parse(safeTrim('﻿{"a":1}')) // ✅
```


## more feature
[more feature](spec/test_spec.js)
