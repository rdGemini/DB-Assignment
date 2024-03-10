Question:1 - Explain the relationship between the "Product" and "Product_Category" entities from the above diagram.
Answer:

In the provided diagram, the relationship between the "Product" and "Product_Category" entities is a one-to-many relationship, where one product category can have multiple products, but each product belongs to only one product category.

This relationship is established through a foreign key constraint in the "Product" table. The "category_id" column in the "Product" table is a foreign key that references the "id" column in the "Product_Category" table. This means that the "category_id" column in the "Product" table holds the id of the product category to which the product belongs.

Question:2 - How could you ensure that each product in the "Product" table has a valid category assigned to it?
Answer:

To ensure that each product in the "Product" table has a valid category assigned to it, you can use a foreign key constraint. This constraint will enforce referential integrity, meaning that the value in the "category_id" column of the "Product" table must exist in the "id" column of the "Product_Category" table.

"ALTER TABLE `product`
ADD CONSTRAINT `fk_product_category`
FOREIGN KEY (`category_id`)
REFERENCES `product_category` (`id`);
"

With this constraint in place, when you try to insert or update a row in the "Product" table, the database will check if the value in the "category_id" column exists in the "id" column of the "Product_Category" table. If it doesn't, the database will reject the operation, ensuring that each product has a valid category assigned to it.
