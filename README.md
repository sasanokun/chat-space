# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization
users table
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false, unique: true|
|password|string|null: false|
  Association
- has_many :groups, through: :users_groups
- has_many :chats

groups table
|Column|Type|Options|
|------|----|-------|
|groupname|string|null: false|
  Association
- has_many :users, through: :users_groups
- has_many :chats

users_groups table
|Column|Type|Options|
|------|----|-------|
|user_id|references|null: false, foreign_key: true|
|group_id|references|null: false, foreign_key: true|
  Association
- belongs_to :group
- belongs_to :user

chats table
|Column|Type|Options|
|------|----|-------|
|chat|text||
|image|text||
|user_id|references|null: false,foreign_key: true|
|group_id|references|null: false,foreign_key: true|
  Association
- belongs_to :group
- belongs_to :user

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
