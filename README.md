# table_setting

## ER diagram

![ER diagram](./public/images/fleamarket_sample_73c.png)

## users

### table

| column         | type   | option                    |
| -------------- | ------ | ------------------------- |
| nickname       | string | null: false, unique: true |
| email          | string | null: false, unique: true |
| password       | string | null: false               |


### association

- has_many :tweets, dependent: :destroy
- has_many :comments, dependent: :destroy

## tweets

### table

| column         | type    | option                         |
| -------------- | ------- | ------------------------------ |
| text           | string  | null: false                    |
| user_id        | integer | null: false, foreign_key: true |

### association

- belongs_to :user
- has_many :comments, dependent: :destroy

## comments

### table

| column      | type    | option                         |
| ----------- | ------- | ------------------------------ |
| text        | string  | null: false                    |
| tweet_id    | string  | null: false, foreign_key: true |
| user_id     | integer | null: false, foreign_key: true |

### association

- belongs_to :user
- belongs_to :comment