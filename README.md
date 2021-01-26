# DB 設計

## user table

| Column             | Type                | Options                 |
|--------------------|---------------------|-------------------------|
| email              | string              | null: false             |
| password           | string              | null: false             |
| name               | string              | null: false             |


### Association

* has_many :item
* has_many :purchase

## item table

| Column             | Type                | Options                 |
|--------------------|---------------------|-------------------------|
| name               | string              | null: false             |
| explain            | text                | null: false             |
| details            | string              | null: false             |
| price              | string              | null: false             |


### Association

- belongs_to :user
* has_one :management

## purchase table

| Column             | Type                | Options                 |
|--------------------|---------------------|-------------------------|
| user               | references          | foreign_key: true       |
| post_code          | integer             | null: false             |
| city               | string              | null: false             |
| house_number       | string              | null: false             |
| phone_number       | integer             | null: false             |
| card_id            | string              | null: false             |

### Association

- belongs_to :user

## management

| Column             | Type                | Options                 |
|--------------------|---------------------|-------------------------|
| user_id            | string              | null: false             |
| item_id            | string              | null: false             |

### Association

- belongs_to :user
- belongs_to :item
