```uml
@startuml

!define MASTER_MARK_COLOR Orange 
!define TRANSACTION_MARK_COLOR DeepSkyBlue

skinparam class {
    BackgroundColor Snow
    BorderColor Black
    ArrowColor Black
}

package "本の帯を売買するショッピングサイト" as target_system {

entity "顧客マスタ" as customer <m_customers><<M,MASTER_MARK_COLOR>> {
  + customer_code [PK]
  --
  pass
  name
  address
  tel
  mail
  del_flag
  reg_date
  }

entity "受注テーブル" as order <d_orders><<T,TRANSACTION_MARK_COLOR>> {
  + order_id [PK]
  --
# item_code [FK]
  purchase_date
  total_price
  }

entity "受注明細テーブル" as orderdetail <d_orders_detail><<T,TRANSACTION_MARK_COLOR>> {
  + order_id [PK]
  + detail_id [PK]
  --
 # item_code [FK]ta
  price
  num
}

entity "商品マスタ" as items <m_items><<M,MASTER_MARK_COLOR>> {
  + item_code [PK]
  --
  # books_id[FK]
  price
  image
}

entity "書籍マスタ" as books <m_books><<M,MASTER_MARK_COLOR>> {
  + books_id [PK]
  --
  item_name
  auther
}

entity "売却テーブル" as sell <d_sell><<T,TRANSACTION_MARK_COLOR>> {
  + slip_code[PK]
  --
  # books_id[FK]
  price
  image
}

entity "売却明細テーブル" as selldetail <d_selldetail><<T,TRANSACTION_MARK_COLOR>> {
  + slip_code[PK]
  + slipdetail_code[PK]
  --
  # books_id[FK]
  # item_code[FK]
}

customer  |o-ri-o{  order
order ||-ri-|{ orderdetail
orderdetail }-do-|| items
items ||-le-|{ books
books ||-le-|{ selldetail
sell ||-ri-{ selldetail

}

@enduml
```
