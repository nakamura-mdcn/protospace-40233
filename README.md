
<!-- usersテーブル -->
| Column             | Type   | Options                   |
| ------------------ | ------ | ----------- |
| name               | string | null: false               |
| email              | string | null: false, unique: true |
| encrypted_password | string | null: false               |
| profile            | text   | null: false               |
| occupation         | text   | null: false               |
| position           | text   | null: false               |

### Association
has_many :prototypes
has_many :comments
has_many :prototype_users
has_many :comment_users

<!-- prototypesテーブル -->
| Column             | Type   | Options                    |
| ------------------ | ------ | ----------- |
| title      | string     | null: false                    |
| catch_copy | text       | null: false                    |
| concept    | text       | null: false                    |
| user       | references | null: false, foreign_key: true |

### Association
has_many :comments
has_many :prototype_users
belongs_to :user


<!-- commentsテーブル -->
| Column             | Type   | Options                   |
| ------------------ | ------ | ----------- |
| user      | references | null: false, foreign_key: true |
| prototype | references | null: false, foreign_key: true |
| content   | text       | null: false                    |

### Association
belongs_to :user
belongs_to :prototype