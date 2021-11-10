# テーブル設計

## users テーブル

| Column               | Type   | Option                      |
| -------------------- | ------ | --------------------------- |
| email                | string | null: folse, unique: true   |
| encrypted_password   | string | null: folse                 |
| name                 | string | null: folse                 |
| profile              | text   | null: folse                 |
| occupation           | text   | null: folse                 |
| position             | text   | null: folse                 |

### Association
has_many :comments
has_many :prototaypes


## prototypes テーブル

|Column     | Type       | Option                         |
|------------------------|--------------------------------|
|title      | string     | null: folse                    |
|catch_copy | text       | null: folse                    |
|concept    | text       | null: folse                    |
|user       | reference  | null: folse, foreign_key: true |

### Association
belongs_to :user
has_many :comments

## comments テーブル

|Column    | Type       | Option                        |
|------------------------|------------------------------|
|content   | text      | null: folse                    |
|prototype | reference | null: folse, foreign_key: true |
|user      | reference | null: folse, foreign_key: true |

### Association
belongs_to :user
belongs_to :prototypes