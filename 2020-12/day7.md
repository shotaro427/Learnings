# 2020-12-01

# Vue3　無限スクロール

## Vue.jsディレクティブ
Vueにおけるディレクティブ
- v-から始まる特別な属性
- ディレクティブの仕事は、属性値の式が変化した時にリアクティブに副作用をDOMに適用すること  
`v-if`や`v-for`など

### カスタムディレクティブ
1. onscrollイベントを付与するディレクティブを作る。
1. window.innerHeightからonscrollイベントを発火させるスクロール量を定義し、それに達したらイベントを発火させる。
1. イベントを発火させたら、次に発火させるスクロール量を再定義する。
1. 2から3の繰り返し。


## Vueのdiv内にスクロールイベントを追加する

```
  created(): void {
    window.addEventListener("scroll", this.logScroll);
  }

  destroyed(): void {
    window.removeEventListener("scroll", this.logScroll);
  }

  logScroll(evt: Event): void {
    console.log("scrolled", evt);
  }
  ```

  ```
  document.querySelector(".task-list")
  ```
  でDivなどを取得
  そのdivに`addEventListene`、`removeEventListener`
  
### ClientHeightとScrollHeightの違い
> `clientHeight`プロパティは、パディングを含む要素の表示可能な高さをピクセル単位で返しますが、境界線、スクロールバー、マージンは返しません。 `scrollHeight`の値は、垂直スクロールバーを使用せずにビューポートのすべてのコンテンツに合わせるために要素が必要とする最小の高さに等しい。

```
scrollHeight = clientHeight + (scrollTopの最大値)
```

つまり
```
if (scrollHeight <= clientHeight + scrollTop) {
    // 最後までスクロール
}
```

# minio
MinioはAmazon S3互換の分散オブジェクトストレージサーバ

```
services:
  minio:
    image: minio/minio:RELEASE.2020-07-31T03-39-05Z
    volumes:
      - minioData:/data1
    ports:
      - 9000:9000
    env_file:
      - .env
    command: server /data1
volumes:
  hoge1:
  hoge2:
```

`.env`に`MINIO_ACCESS_KEY`と`MINIO_SECRET_KEY`を設定  
`localhost:9000`にアクセス


# moment 
先週や先月の出し方  
```
// 先週
moment().add('week', -1).format("YYYY/MM/DD HH:mm:ss")
// 先月
moment().add('month', -1).format("YYYY/MM/DD HH:mm:ss")
```

# typeorm
`@Check()`デコレーター  
このデコレータを使用すると、特定の1つまたは複数の列のデータベースチェック制約を作成できる。このデコレータは、エンティティ自体にのみ適用できる。

ex)
```
@Entity()
@Check(`"firstName" <> 'John' AND "lastName" <> 'Doe'`)
@Check(`"age" > 18`)
export class User {

    @Column()
    firstName: string;

    @Column()
    lastName: string;

    @Column()
    age: number;
}
```
