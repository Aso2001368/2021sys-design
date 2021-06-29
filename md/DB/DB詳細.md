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
|属性名| 型 | PK | NN | FK |
|-----|----|----|----|----|
|detail_id|bigint(20)|NOT NULL|AUTO_INCREMENT|| 
|order_id|bigint(20)|NOT NULL|DEFAULT '0'| 
|item_code|int(11)|NOT NULL||| 
|price|int(11)|NOT NULL|||
|num|int(11)|NOT NULL|PRIMARY KEY (detail_id,order_id)||

m_customers
|属性名| 型 | PK | NN | FK |
|-----|----|----|----|----|

m_category
|属性名| 型 | PK | NN | FK |
|-----|----|----|----|----|

m_items
|属性名| 型 | PK | NN | FK |
|-----|----|----|----|----|
