`Object.entries()`でオブジェクトを配列に変換する

`Object.fromEntries()`で元に戻せる

```js
const objA = { a: 1, b: 2, c: 3, d: true };

const arrA = Object.entries(objA);
console.log(arrA) // > Array [Array ["a", 1], Array ["b", 2], Array ["c", 3], Array ["d", true]]

const fromEntriesA = Object.fromEntries(arrA)
console.log(fromEntriesA) // > Object { a: 1, b: 2, c: 3, d: true }
```

これを応用すればオブジェクト同士の加算処理なども行える

※ 前提としてobjA ∋ objBでobjBには数値のプロパティしか存在しない

```js
const objA = { a: 1, b: 2, c: 3, d: true };
const objB = { a: 2, b: 2, c: 6 };

const objC = {
  ...objA, // まずobjAを展開
  ...Object.fromEntries(
    Object.entries(objB).map(([key, value]) => [key, value + objA[key]])
  ), // objBのプロパティを配列に変換して、対応するobjAの値と加算
};

console.log(objC) // > Object { a: 3, b: 4, c: 9, d: true }
```
