# README

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|nickname|string|add_index:usres, :nickname:true|
|mail_address|string|add_index:usres, :mail_address:true|

### Association
- has_many :groups_users
- has_many :groups, through: :groups_users
- has_many :messages



## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|group_name|string|null: false, foreign_key: true|

### Association
- has_many :groups_users
- has_many :users, through: :groups_users
- has_many :messages




## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|string|null: false, foreign_key: true|
|group_name|string|null: false, foreign_key: true|
|image|string|

### Association
- belongs_to :group
- belongs_to :user


## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user