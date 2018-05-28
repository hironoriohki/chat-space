## membersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## userテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, index: true|
|email|string|null: false|

### Association
- has_many :messages
- has_many :members
- has_many :groups,through::members

## groupsテーブル
|Column|Type|Options|
|------|----|------|
|name|string|index:true,null:false|

### Association
- has_many :messages
- has_many :members
- belongs_to :users,through::members

## messagesテーブル
|Column|Type|Options|
|------|----|------|
|coments|text|
|image|string|
|user_id|references|foreign_key:true|
|group_id|references|foreign_key:true|

### Association
 - belongs_to :group
 - belongs_to :user
