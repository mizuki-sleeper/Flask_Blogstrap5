# Flask_Blogstrap5

Flask と Bootstra5 の練習でつくりました。

デモはこちらです
https://youtu.be/dyQ7ilayX4M

SQL-Alchemy でのデータベース操作や、Migration、
flask_login や wtforms を使用しています。

# Flask_Blogstrap5 〜ブログアプリ〜

### users テーブル

| フィールド名  | データ型     | 説明                                         |
| ------------- | ------------ | -------------------------------------------- |
| id            | Integer      | ユーザーの一意の識別子                       |
| email         | String(64)   | ユーザーのメールアドレス                     |
| username      | String(64)   | ユーザー名                                   |
| password_hash | String(128)  | パスワードのハッシュ化された値               |
| administrator | String(1)    | 管理者かどうかを示すフラグ（"1" または "0"） |
| post          | Relationship | ユーザーに関連するブログ投稿の関係性         |
