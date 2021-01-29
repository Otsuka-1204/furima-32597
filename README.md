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

* has_many :items
* has_many :managements

## item table

| Column               | Type                | Options                 |
|----------------------|---------------------|-------------------------|
| name                 | string              | null: false             |
| explain              | text                | null: false             |
| price                | integer             | null: false             |
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
| management_id      | references          | foreign_key: true       |
| post_code          | integer             | null: false             |
| prefecture_id      | string              | null: false             |
| municipality       | string              | null: false             |
| address            | integer             | null: false             |
| building_name      | string              | null: false             |
| phone_number       | integer             | null: false             |


### Association

- belongs_to :management

## management

| Column             | Type                | Options                 |
|--------------------|---------------------|-------------------------|
| user_id            | string              | null: false             |
| item_id            | string              | null: false             |

### Association

- belongs_to :user
- belongs_to :item
