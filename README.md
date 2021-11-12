# テーブル設計

<!-- prototypeテーブル -->

| Column             | Type       | Options                       |
| ------------------ | ---------- | ----------------------------- |
| title              | string     | null: false                   |
| catch_copy         | text       | null: false                   |
| concept            | text       | null: false                   |
| user               | reference  | null: false ,foreign_key: true|

- has_many :comments
- belongs_to :user

<!-- userテーブル -->

| Column             | Type   | Options                   |
| ------------------ | ------ | ------------------------- |
| email              | string | null: false , unique: true|
| encrypted_password | string | null: false               |
| name               | string | null: false               |
| profile            | text   | null: false               |
| occupation         | text   | null: false               |
| position           | text   | null: false               |

- has_many :prototypes
- has_many :comments

<!-- commentsテーブル -->

| Column             | Type      | Options                       |
| ------------------ | --------- | ----------------------------- |
| content            | text      | null: false                   |
| prototype          | reference | null: false ,foreign_key: true|
| user               | reference | null: false ,foreign_key: true|

- belongs_to :prototype
- belongs_to :user
