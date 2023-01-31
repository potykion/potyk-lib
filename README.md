# `potyk-lib`

Everyday dev utils like date utils, FP utils, collection utils and so on

## FP

### `falsy` / `nullish`

Similar
to [JS optional chaining and nullish coalescing](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Optional_chaining)

```python
from potyk_lib.fp.maybe import *

assert falsy(1).if_some(lambda i: i + 1).get() == 2
assert falsy(None).if_some(lambda i: i + 1).if_nothing(lambda: 3).get() == 3

assert falsy(item).field
assert falsy(None).field is None

assert isinstance(falsy(None), Nothing)
assert isinstance(falsy(0), Nothing)
assert isinstance(falsy(1), Some)

assert isinstance(nullish(None), Nothing)
assert isinstance(nullish(0), Some)
assert isinstance(nullish(1), Some)
```