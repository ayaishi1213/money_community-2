## テーブル設計

## usersテーブル

| Column        | Type    | Options     |
| ------------- |-------- | ----------- |
| email         | string  | null: false |
| password      | string  | null: false |
| name          | string  | null: false |
| nickname      | string  | null: false |
| age_range_id  | integer | null: false |  #Active hash使う
| occupation    | text    | null: false |
| profile       | text    | null: false |

### Association
- has_many  :posts
- has_many  :comments


## postsテーブル
| Column        | Type      | Options                       |
| ------------- |---------- | ----------------------------- |
| nickname      | string    | null: false                   |
| age_range_id  | integer   | null: false                   |  #Active hash使う
| title         | string    | null: false                   |
| article       | text      | null: false                   |
| user          |references | null: false,foreign_key: true |

## Association
- belongs_to :user
- has_many  :comments


## commentsテーブル
| Column                 | Type       | Options                       |
| ---------------------- | ---------- | ----------------------------- |
| user                   | references | null: false,foreign_key: true |
| post                   | references | null: false,foreign_key: true |
| comment                | text       | null: false                   |

## Association
- belongs_to :user
- belongs_to :post
