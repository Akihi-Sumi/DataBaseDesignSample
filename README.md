# DataBaseDesignSample
# Chatspace DB設計
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|username|string|null: false|
|groups_id|integer|null: false, foreign_key: true|
### Association
- has_many :messages
- has_many :groups

## messageテーブル
|Column|type|Options|
|------|----|-------|
|text|text|null: false|
|image|text|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user

## groupsテーブル
|Column|type|Options|
|------|----|-------|
|group_name|string|null: false|
|users_id|integer|null: false, foreign_key: true|
### Association
- has_many :users

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user

## create_groupsテーブル
|Column|type|Options|
|------|----|-------|
|user_id|
|group_name|
|group_id|
|users_name|
|users_id|
### Association
- belongs_to :user

## edit_groupテーブル
|Column|type|Options|
|------|----|-------|
|user_id|
|group_id|
|users_name|
|users_id|
|group_name|
|group_id|
### Association
- has_many :users

## edit_userテーブル
|Column|type|Options|
|------|----|-------|
|user_id|
|user_name|
|email|
### Association
- belongs_to :user
