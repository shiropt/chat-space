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

```ruby

## usersテーブル
|Column |Type   |Options                                     |
|-------|-------|--------------------------------------------|
|name   |string |null: false, index: true                    |
|email  |string |null: false, unique: true                   |
|pass   |string |null: false                                 |

### Association
  has_many :groups, through: :Users_Groups
  has_many :massages


## messagesテーブル
|Column |Type   |Options                                    |
|-------|-------|-------------------------------------------|
|body   |text   |foreign_key: true                          |
|image  |string |foreign_key: true                          |

### Association
  belong_to :user
  belong_to :group
  



# groupsテーブル
|Column     |Type   |Options                                    |
|-----------|-------|-------------------------------------------|
|name       |string |null: false,  index: true                  |

### Association
  has_many :users, through: :Users_Groups
  has_many :messages




# User_Groupテーブル
|Column     |Type   |Options                        |
|-----------|-------|-------------------------------|
|user_id    |integer |null: false, foreign_key: true|
|group_id   |integer |null: false, foreign_key: true|

### Association
  belongs_to :user
  belongs_to :group

```