
## Input

```javascript
function bar(a) {
  let x = [a];
  let y = {};
  (function () {
    y = x[0][1];
  })();

  return y;
}

export const FIXTURE_ENTRYPOINT = {
  fn: bar,
  params: [['val1', 'val2']],
  isComponent: false,
};

```

## Code

```javascript
import { c as _c } from "react/compiler-runtime";
function bar(a) {
  const $ = _c(2);
  let y;
  if ($[0] !== a) {
    const x = [a];
    y = {};

    y = x[0][1];
    $[0] = a;
    $[1] = y;
  } else {
    y = $[1];
  }
  return y;
}

export const FIXTURE_ENTRYPOINT = {
  fn: bar,
  params: [["val1", "val2"]],
  isComponent: false,
};

```
      
### Eval output
(kind: ok) "val2"