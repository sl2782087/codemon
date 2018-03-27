## flatten array 平铺数组

### 版本一

```javascript
Array.prototype.flatten = function() {
	return this.reduce((a, b) => (Array.isArray(b) ? a.concat(b.flatten()) : a.concat([b])), []);
};

//[1,[2,[3]]].flatten() -> [1,2,3]
```

### 版本二

```javascript
Array.prototype.flatten = function() {
	return [].concat(...this.map(a => (Array.isArray(a) ? a.flatten() : a)));
};

//[1,[2,[3]]].flatten() -> [1,2,3]
```

## Returns all unique values of an array 数组去重

```javascript
Array.prototype.onlyone = function() {
	return [new Set(...this)];
};

//[1,2,3,1].onlyone() -> [1,2,3]
```
