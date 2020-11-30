# 2020-11-30

# Bootstrap

## 等幅グリッド
### `col`と`row`

```
<div class="container-fluid">
  <div class="row">
    <div class="col">A</div>
    <div class="col">B</div>
    <div class="col">C</div>
    <div class="col">D</div>
    <div class="col">E</div>
  </div>
</div>
```


`w-100`を入れることで改行可能
```
<div class="container-fluid">
  <div class="row">
    <div class="col">A</div>
    <div class="col">B</div>
    <div class="col">C</div>
    <div class="w-100"></div>
    <div class="col">D</div>
    <div class="col">E</div>
  </div>
</div>
```


`col-{n}`で幅を指定できる。幅は12分割した内のいくつ使うかで指定  
`col-3`で3/12の横幅を使用


