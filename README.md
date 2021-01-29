# DB 設計

## user table

| Column             | Type                | Options                 |
|--------------------|---------------------|-------------------------|
| nickname           | string              | null: false             |
| email              | string              | null: false             |
| password           | string              | null: false             |
| first_name         | string              | null: false             |
| last_name          | string              | null: false             |
| first_name_kana    | string              | null: false             |
| last_name_kana     | string              | null: false             |
| birthday           | string              | null: false             |

### Association

* has_many :item
* has_many :purchase

## item table

| Column               | Type                | Options                 |
|----------------------|---------------------|-------------------------|
| name                 | string              | null: false             |
| explain              | text                | null: false             |
| price                | string              | null: false             |
| status_id            | string              | null: false             |
| shipping_price_id    | string              | null: false             |
| prefecture_id        | string              | null: false             |
| shipping_delivery_id | string              | null: false             |
| category_id          | string              | null: false             |


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
