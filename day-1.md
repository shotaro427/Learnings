# 2020-11-24

## Vue
テキストのインプット
```
<input v-model="message" placeholder="edit me">
<p>Message is: {{ message }}</p>
```

[参照](https://jp.vuejs.org/v2/guide/forms.html)

## TypeOrm

### TreeRepository

```
protected roomRepository: TreeRepository<RoomEntity>
```
[参照](https://github.com/typeorm/typeorm/blob/master/docs/tree-entities.md)


`createDescendantsQueryBuilder`  
ツリー構造内の子孫を取得するためにしようする

`findTrees`
