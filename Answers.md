ANSWER 1-
The relationship between the “Product” and “Product_Category” entities in the diagram is a One-to-Many relationship.
This means that one record in the “Product_Category” table can correspond to multiple records in the “Product” table. However, each product can belong to only one product category.
This relationship is typically represented in the database by having a foreign key (in this case, category_id) in the “Product” table that references the primary key (id) of the “Product_Category” table. This allows for efficient querying and data integrity.
For example, if you have a product category called “Electronics”, multiple products like “Laptop”, “Smartphone”, and “Tablet” could all belong to this category, hence forming a one-to-many relationship.

ANSWER 2-

To ensure that each product in the “Product” table has a valid category assigned to it, we can use foreign key constraints in this database.
In this case, the category_id field in the “Product” table is a foreign key that references the id field in the “Product_Category” table. 
A foreign key constraint ensures that the value in the category_id field always points to an existing record in the “Product_Category” table.

To define foreign key constrain in SQL:

ALTER TABLE Product
ADD CONSTRAINT FK_Product_ProductCategory
FOREIGN KEY (category_id) REFERENCES Product_Category(id)
ON DELETE SET NULL
ON UPDATE CASCADE;
