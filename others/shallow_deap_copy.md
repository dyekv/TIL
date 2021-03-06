# シャローコピーとディープコピーについて

オブジェクト（配列など）をコピーする時の方法の違い

シャローコピーは浅いコピーで表面的なコピーである

```js
var arr = [1,2,3,4]
var arrCopy = arr
arr.push(5)

console.log(arr) // [1,2,3,4,5]
console.log(arrCopy) // [1,2,3,4,5]
```

コピーしてもarrとarrCopyは同じ配列を指すので変更がどちらにも反映される

これは、変数に格納されているのがオブジェクト本体ではなく、そのオブジェクトの座標だからである

C言語で言うところのポインタのようなもの

ディープコピーは別のオブジェクトを作成するコピーである

```js
var arr = [1,2,3,4]
var arrCopy = arr.slice()
arr.push(5)

console.log(arr) // [1,2,3,4,5]
console.log(arrCopy) // [1,2,3,4]
```

この場合はarrCopyは新しく生成された配列を指すのでarrの変更は反映されない

#### 通常の代入ではシャローコピーになってしまうため、破壊的な操作を行う際は注意が必要

# 破壊的メソッドと非破壊的メソッド

配列のメソッドには破壊的なメソッドと非破壊的なメソッドがある

破壊的なメソッドは配列自体を操作するメソッドや、元配列に影響を及ぼす

```js
var arr = [1,2,3,4]
var arrPickup = arr.splice(2,2) // index2 ~ 2つを切り出す

console.log(arr) // [1,2]　<- 元の配列に影響を及ぼす（破壊的）
console.log(arrPickup) // [3,4]
```

非破壊的なメソッドは配列はそのままでコピーを作り、コピーに対して操作を行う

```js
var arr = [1,2,3,4]
var arrPickup = arr.slice(2,4) // index2 ~ index4未満を返す

console.log(arr) // [1,2,3,4]
console.log(arrPickup) // [3,4]
```

破壊的なメソッドの例：`splice` `push` `sort` など

非破壊的なメソッドの例：`slice` `map` `filter` など

非破壊的なメソッドはオブジェクトをコピーするため、先述のディープコピーでも用いられる

例えば`slice`は指定した範囲の配列を作成するが、引数が空だと同じ配列（コピー）を作成する

# 多次元配列のディープコピー

`slice`でディープコピーが出来るのは１次元配列のみである [[参考]](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/Array/slice)

配列の中身はシャローコピーであるため、配列の中に配列がある場合は完全なディープコピーにならない

```js
var arr = [[11,12,13],[21,22,23],[31,32,33]]
var arrCopy = arr.slice()

arr[0].push(14)

console.log(arr[0]) // [11,12,13,14]
console.log(arrCopy[0]) // [11,12,13,14]

```

この場合は`map`を使い、内側の配列をひとつずつディープコピーすると良い

```js
var arr = [[11,12,13],[21,22,23],[31,32,33]]
var arrCopy = arr.map(arrChild => arrChild.slice())

arr[0].push(14)

console.log(arr[0]) // [11,12,13,14]
console.log(arrCopy[0]) // [11,12,13]
```
