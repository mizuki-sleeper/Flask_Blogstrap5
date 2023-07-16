# Flask_Blogstrap5 〜ブログアプリ〜

Flask と Bootstra5 の練習でつくりました。<br>
デモはこちらです → https://youtu.be/dyQ7ilayX4M

## 機能

-   ブログ一覧
-   カテゴリー別記事一覧
-   記事検索
-   記事詳細
-   プロフィール
-   エラーページ
-   ユーザー認証と管理 (UserMixin, Werkzeug)
-   ユーザー登録、ログイン、ログアウト
-   ブログ投稿、カテゴリー、お問い合わせの作成、表示、削除
-   フォーム(バリデーション,入力制限)
-   データベースのセットアップとマイグレーション

## 技術構成

-   Python ３
    -   Flask
    -   SQLAlchemy ORM
    -   Flask-Migrate 拡張機能
    -   Flask-Login 拡張機能
    -   Werkzeug セキュリティモジュール
    -   PIL ライブラリ
    -   WTForms
    -   Blueprint
-   HTML
-   Bootstrap5
-   Prettier

## SQLite スキーマ設定

### User (ユーザー)

| フィールド名  | 説明                       | データ型     |
| ------------- | -------------------------- | ------------ |
| id            | ユーザー ID (主キー)       | Integer      |
| email         | ユーザーのメールアドレス   | String(64)   |
| username      | ユーザー名                 | String(64)   |
| password_hash | パスワードのハッシュ値     | String(128)  |
| administrator | 管理者かどうかを示すフラグ | String(1)    |
| post          | ユーザーの投稿との関連性   | Relationship |

### BlogPost (ブログ投稿)

| フィールド名   | 説明                           | データ型     |
| -------------- | ------------------------------ | ------------ |
| id             | 投稿 ID (主キー)               | Integer      |
| user_id        | 投稿のユーザー ID (外部キー)   | Integer      |
| category_id    | 投稿のカテゴリー ID (外部キー) | Integer      |
| date           | 投稿の日時                     | DateTime     |
| title          | 投稿のタイトル                 | String(140)  |
| text           | 投稿の本文                     | Text         |
| summary        | 投稿の要約                     | String(140)  |
| featured_image | 投稿の特集画像                 | String(140)  |
| author         | 投稿の著者との関連性           | Relationship |

### BlogCategory (ブログカテゴリー)

| フィールド名 | 説明                     | データ型     |
| ------------ | ------------------------ | ------------ |
| id           | カテゴリー ID (主キー)   | Integer      |
| category     | カテゴリー名             | String(140)  |
| posts        | カテゴリーに関連する投稿 | Relationship |

### Inquiry (お問い合わせ)

| フィールド名 | 説明                           | データ型    |
| ------------ | ------------------------------ | ----------- |
| id           | お問い合わせ ID (主キー)       | Integer     |
| name         | お問い合わせ者の名前           | String(64)  |
| email        | お問い合わせ者のメールアドレス | String(64)  |
| title        | お問い合わせのタイトル         | String(140) |
| text         | お問い合わせの内容             | Text        |
| date         | お問い合わせの日時             | DateTime    |

## 開発方法

```
# パッケージをinstall
$ pip install -r requirements.txt

# データベースを初期化（初回のみ）
$ python init_db.py

# 開発サーバーを起動(localhost:5000)
$ python app.py

```
