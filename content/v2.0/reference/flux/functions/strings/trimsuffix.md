---
title: strings.trimSuffix() function
description: >
  The `strings.trimSuffix()` function removes a suffix from a string.
  Strings that do not end with the suffix are returned unchanged.
menu:
  v2_0_ref:
    name: strings.trimSuffix
    parent: Strings
weight: 301
related:
  - /v2.0/reference/flux/functions/strings/trim
  - /v2.0/reference/flux/functions/strings/trimleft
  - /v2.0/reference/flux/functions/strings/trimright
  - /v2.0/reference/flux/functions/strings/trimprefix
  - /v2.0/reference/flux/functions/strings/trimspace
---

The `strings.trimSuffix()` function removes a suffix from a string.
Strings that do not end with the suffix are returned unchanged.

_**Output data type:** String_

```js
import "strings"

strings.trimSuffix(v: "123_abc", suffix: "abc")

// returns "123_"
```

## Parameters

### v
The string value to trim.

_**Data type:** String_

### suffix
The suffix to remove.

_**Data type:** String_

## Examples

###### Remove a suffix from all values in a column
```js
import "strings"

data
  |> map(fn: (r) => ({
      r with
      sensorID: strings.trimSuffix(v: r.sensorId, suffix: "_s12")
    })
  )
```