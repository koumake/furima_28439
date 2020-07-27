# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

## groups_usersテーブル
|Column|Type|Options|
|:---:|:---:|:---:|
|name|string|null: false|
|name-kana|string|null: false|
|email|string|null: false|
|birthday|integer|null: false|
|nickname|string|null: false|
### Association
- has_many :exhibitions
- has_many :purchases
- has_many :comments

## groups_exhibitionsテーブル
|Column|Type|Options|
|:---:|:---:|:---:|
|item|string|null: false|
|item-image|string|null: false|
|price|integer|null: false|
|category|string|null: false|
|condition|string|null: false|
|delivery-fee|string|null: false|
|from|string|null: false|
|days|string|null: false| 
|item-about|text|null: false|
### Association
- belongs_to :users
- belongs_to :purchases
- has_many :comments


## groups_purchasesテーブル
|Column|Type|Options|
|:---:|:---:|:---:|
|card-number|integer|null: false|
|deadline|integer|null: false|
|security-code|integer|null: false|
|postal-code|integer|null: false| 
|prefecture|string|null: false|
|city|string|null: false|
|address|integer|null: false|
|building|string||
|tel-number|integer|null: false|
### Association
- belongs_to :users
- has_many :exhibitions
- has_many :comments


## groups_commentsテーブル
|Column|Type|Options|
|:---:|:---:|:---:|
|content|text|null: false|
|created-at|datetime|null: false|
|item_id|references|null: false, foreign_key: true|
|user_id|references|null: false, foreign_key: true| 
## Association
- belongs_to :users
- belongs_to :exhibitions
- belongs_to :purchases