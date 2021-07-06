### データベース詳細
*****

d_purchase

|属性名| 型 | PK | NN | FK |
|-----|----|----|----|----|
|order_id|bigint(20)|〇|〇||
|customer_code|varchar(50)||〇|| 
|purchase_date|date||〇||
|total_price|int(11)||〇||

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
|customer_code|varchar(50)||||
|pass|varchar(50)||||
|name|varchar(20)||||
|address|varchar(100)||||
|tel|varchar(20)||||
|mail|varchar(100)|| ||
|del_flag|int(1)||||
|reg_date|date||||

m_category
|属性名| 型 | PK | NN | FK |
|-----|----|----|----|----|
|category_id|int(11)|NOT NULL|AUTO_INCREMENT||
|name|varchar(20)|NOT NULL|||
|reg_date|date|NOT NULL|PRIMARY KEY (category_id)||

m_items
|属性名| 型 | PK | NN | FK |
|-----|----|----|----|----|
|item_code|int(11)|NOT NULL|DEFAULT '0'||
|item_name|varchar(50)|NOT NULL|||
|price|int(11)|NOT NULL|||
|category_id|int(11)|NOT NULL|||
|image|varchar(200)|NOT NULL|||
|detail|varchar(500)|DEFAULT NULL|||
|del_flag|int(11)|DEFAULT NULL|||
|reg_date|date|NOT NULL|PRIMARY KEY (item_code)|FOREIGN KEY PK_category(category_id) REFERENCES m_category(category_id)|







