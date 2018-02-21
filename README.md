datebase_structure

## Customers table

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false, unique: ture|
|password|string|null: false,|
|image|string|null: false|
|profile|text||

### Association
- has_many :suppliers, through: :matchings
- has_many :messages
- has_many :customer_reviews
- has_many :supplier_reviews


## Suplliers table

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false, unique: ture|
|password|string|null: false,|
|image|string|null: false|
|high_school|string||
|university|string|null: false|
|faculty|string|null: false|
|admission_process|string|null: false|
|online|integer|null: false|
|offline|integer|null: false|
|club_circle|text||
|seminar|text||
|profile_self|text||
|profile_study|text||

### Association
- has_many :customers, through: :matchings
- has_many :messages
- has_many :customer_reviews
- has_many :supplier_reviews


## Matchings table

|Column|Type|Options|
|------|----|-------|
|customer_id|integer|null: false,foreign_key:true|
|supplier_id|integer|null: false,foreign_key:true|

### Association
- belongs_to :customer
- belongs_to :supplier
- has_many :messages


## messages table

|Column|Type|Options|
|------|----|-------|
|body|text||
|matchong_id|integer|null: false,foreign_key:true|
|customer_id|integer|foreign_key:true|
|supplier_id|integer|foreign_key:true|

### Association
- belongs_to :customer
- belongs_to :supplier
- belongs_to :matching


## Customer_reviews table

|Column|Type|Options|
|------|----|-------|
|review|text|null: false|
|customer_id|integer|null: false,foreign_key:true|
|supplier_id|integer|null: false,foreign_key:true|

### Association
- belongs_to :customer
- belongs_to :supplier


## Supplier_reviews table

|Column|Type|Options|
|------|----|-------|
|review|text|null: false|
|customer_id|integer|null: false,foreign_key:true|
|supplier_id|integer|null: false,foreign_key:true|

### Association
- belongs_to :customer
- belongs_to :supplier

