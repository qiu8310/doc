>
> [ruanyifeng](http://es6.ruanyifeng.com/#docs/generator) 
>
> [ponyfoo](https://ponyfoo.com/articles/es6-generators-in-depth)
>

```js
function* fab(n) {
  let [a, b, count] = [1, 2, 2];

  if (n <= 0) return ;
  if (n > 0) yield a;
  if (n > 1) yield b;

  while (count < n) {
    [a, b] = [b, a + b];
    yield b;
    count++;
  }
}
```

## 与 Iterator 接口的关系

```js
let f = fab();
f[Symbol.iterator]() === f;
```


## 三种将 generator 变成数组的方法

1. `Array.from(fab(10))`
2. `[...fab(10)]`
3. `for (let n of fab(10)) { ... }`


## 在一个 generator 中调用另一个 generator 需要使用 `yield*`

```js
function* wrapFab() {
  yield 'start';
  yield* fab(3);
  yield 'end';
}

console.log([...wrapFab()]);
```

> 实际上，任何数据结构只要有 Iterator 接口，就可以被 yield* 遍历
> 另外， `yield* generator()` 可以得到 generator 的 return 值

## ES6 中字符串数组者是个 generator

```js
yield* 'abc';       // => yield 'a'; yield 'b'; yield 'c';
yield* [1, 2, 3];   // => yield 1;   yield 2;   yield 3;
```





