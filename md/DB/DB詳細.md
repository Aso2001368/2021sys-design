### データベース詳細
*****

d_purchase

|属性名| 型 | PK | NN | FK |
|-----|----|----|----|----|
|order_id|bigint(20)|NOT NULL|AUTO_INCREMENT||
|customer_code|varchar(50)|NOT NULL||| 
|purchase_date|date|NOT NULL|||
|total_price|int(11)|NOT NULL|PRIMARY KEY(order_id)||

d_purchase_detail
