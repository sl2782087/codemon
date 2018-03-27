## flatten array 平铺数组

### 版本一

```javascript
Array.prototype.flatten = function() {
  return this.reduce(
    (a, b) => (Array.isArray(b) ? a.concat(b.flatten) : a.concat([b])),
    []
  );
};
```

### 版本二

```javascript
Array.prototype.flatten = function() {
  return [].concat(...this.map(a => (Array.isArray(a) ? a.flatten() : a)));
};
```

