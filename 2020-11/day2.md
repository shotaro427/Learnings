# 2020-11-25

## JS Date Format

```
JavaScript
/** 現在のDateオブジェクト作成 */
var d = new Date();

/** 文字列に日付をフォーマットする */
var formatted = `
${d.getFullYear()}-
${d.getMonth()+1}-
${d.getDate()}
`.replace(/\n|\r/g, '');

console.log(formatted);
  /// => 2019-1-4
1
2
3
4
5
6
7
8
9
10
11
12
/** 現在のDateオブジェクト作成 */
var d = new Date();
 
/** 文字列に日付をフォーマットする */
var formatted = `
${d.getFullYear()}-
${d.getMonth()+1}-
${d.getDate()}
`.replace(/\n|\r/g, '');
 
console.log(formatted);
  /// => 2019-1-4
  ```