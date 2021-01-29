# DB 設計

## user table

| Column             | Type                | Options                 |
|--------------------|---------------------|-------------------------|
| nickname           | string              | null: false             |
| email              | string              | unique: true            |
| encrypted_password | string              | null: false             |
| first_name         | string              | null: false             |
| last_name          | string              | null: false             |
| first_name_kana    | string              | null: false             |
| last_name_kana     | string              | null: false             |
| birthday           | date                | null: false             |

### Association

* has_many :items
* has_many :managements

## item table

| Column               | Type                | Options                 |
|----------------------|---------------------|-------------------------|
| user                 | references          | foreign_key: true       |
| name                 | string              | null: false             |
| explain              | text                | null: false             |
| price                | integer             | null: false             |
| status_id            | integer             | null: false             |
| shipping_price_id    | integer             | null: false             |
| prefecture_id        | integer             | null: false             |
| shipping_delivery_id | integer             | null: false             |
| category_id          | integer             | null: false             |


### Association

- belongs_to :user
* has_one :management

## purchase table

| Column             | Type                | Options                 |
|--------------------|---------------------|-------------------------|
| management         | references          | foreign_key: true       |
| post_code          | string              | null: false             |
| prefecture_id      | integer             | null: false             |
| municipality       | string              | null: false             |
| address            | string              | null: false             |
| building_name      | string              |                         |
| phone_number       | string              | null: false             |


### Association

- belongs_to :management

## management

| Column             | Type                | Options                 |
|--------------------|---------------------|-------------------------|
| user               | references          | foreign_key: true       |
| item               | references          | foreign_key: true       |

### Association

- belongs_to :user
- belongs_to :item
* has_one :purchase
