# DB 設計

## ユーザー管理機能

| Column             | Type                | Options                 |
|--------------------|---------------------|-------------------------|
| email              | string              | null: false             |
| password           | string              | null: false             |
| name               | string              | null: false             |


### Association

## 商品出品機能

| Column             | Type                | Options                 |
|--------------------|---------------------|-------------------------|
| user               | references          | foreign_key: true       |
| title              | string              | null: false             |
| price              | string              | null: false             |

### Association

- belongs_to :user

## 商品購入機能

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
