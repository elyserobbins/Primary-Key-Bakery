
# Team 6 Mist 4610 Group Project 1




## Team Name: 
47114 Group 6


## Team Members:
1. [Thanh (Randy) Bui](https://github.com/thanh8ui)
2. [Luke Eckert](https://github.com/Luke-Eckert) 
3. [Claire Lee](https://github.com/clairerlee)
4. [Elyse Robbins](https://github.com/elyserobbins)
5. [Elliot Wallace](https://github.com/e8w-9837)
## Problem Description:
The task at hand is to model and build a relational database for the general workings of a bakery business. The central entity in the model is the Bakery entity, representing each physical bakery location that the company owns and operates in various areas. The bakery operates in conjunction with the products it sells, the ingredients it sources, the suppliers it works with, and the customers who purchase from them, whether in-store or via special orders.

We are interested in accurately modeling these relationships, generating sample data, and populating the entities and their attributes with this sample data. Furthermore, we are interested in performing functioning queries on this data to provide valuable business insights about the bakery’s operations, such as tracking best-selling products, monitoring ingredient inventory, evaluating supplier reliability, and analyzing customer purchasing trends.

## Data Model: 
Our Data model is a bakery, named Primary Key Pastries. We have mapped out the data model to accurately model the data needed for this bakery business, using essential entities and their relationships with one another to correctly support different facets of the business such as staffing, inventory, and payments
First off, the supplier entity represents the different vendors from which our bakery gets its raw materials. Within this entity, we have the primary key (supplierID), as well as the name of supplier, their contact info, and information about the product that they provide. Suppliers can provide multiple ingredients. Each ingredient is identified by a unique IngredientsID and has a name, a reference to its supplier (foreign key), a quantity, a cost per unit, and an expiration date.

Ingredients and Products have a many to many relationship - connected by a table named “Products_Ingredients”. The Products entity contains all items that are available for sale in the bakery, which includes attributes such as the Name, Category, Price, and Availability of the product. In the Product_Ingredients entity there are two foreign keys pulled from Products (ProductID) and Ingredients (IngredientID), as well as the attribute Quantity required for making each product. 

The Customers table maintains records of customer details such as names, contact information, and loyalty program status. Customers place Orders, forming a one-to-many relationship where a customer can have multiple orders. The Orders entity contains order-specific details such as order date, total cost, and order status. Since each order consists of multiple products, we introduce the Order_Items table, which links Orders to Products in a many-to-many relationship. This table tracks the quantity of each product in an order and its subtotal.

The Products entity also has a many to many relationship with the Orders entity, connected by the associative entity Order_Items. Within the Order_Items table, there is its own primary key (OrderItemID), as well as two forging keys that are pulled from the Orders entity and the Products entity. Regarding the attributes in the Order_Items table, there is the quantity of the items in the order, as well as the subtotal of the order. Regarding the Orders entity, it has its own primary key (OrderID), as well as a foreign key from the Customers table. Regarding its own attributes not related to other tables, the OrderDate, OrderStatus, and TotalCost of the order is also tracked within the Orders table. Related to the Orders entity is the Customers entity, as one customer can have many orders. Within the Customers entity, there is a primary key (CustomerID), as well as the name of the customer, contact information, and the customer's status within the bakery’s loyalty program.
    
The Employees table records bakery staff details, including their names, roles, salaries, and work schedules. Employees are assigned to specific tasks via the Employee_Assignments table, which tracks the task description and assignment dates. Employees also play a role in fulfilling orders, which is represented by the Employees_Orders table. This entity captures which employees are responsible for each order and their roles in the process (e.g., cashier, baker, delivery).


![App Screenshot](https://snipboard.io/Hp0kri.jpg
)
## Data Dictionary:
Table: Customers
![App Screenshot](https://snipboard.io/doVt8y.jpg)

Table: Employee_Assignment
![App Screenshot](https://snipboard.io/tuzovq.jpg)

Table: Employees
![App Screenshot](https://snipboard.io/i9eoMd.jpg)

Table: Employee_Orders
![App Screenshot](https://snipboard.io/MaspxH.jpg)

Table: Ingredients
![App Screenshot](https://snipboard.io/VEKtHj.jpg)

Table: Order_Items
![App Screenshot](https://snipboard.io/VY8Lrl.jpg)

Table: Orders
![App Screenshot](https://snipboard.io/2ElwGO.jpg)

Table: Product_Ingredients
![App Screenshot](https://snipboard.io/vk6YZV.jpg)

Table: Products 
![App Screenshot](https://snipboard.io/OarQLF.jpg)

Table: Suppliers
![App Screenshot](https://snipboard.io/ez601a.jpg)


## Queries: 
![App Screenshot](https://snipboard.io/36tSPk.jpg)

### Simple Queries: 

1. Query #1 retrieves all orders placed by a specific customer (CustomerID = 1010). It allows bakery managers to track customer purchase history and understand buying habits. By analyzing these orders, managers can identify customer preferences, recommend relevant products, and offer personalized promotions or loyalty rewards.
![App Screenshot](https://snipboard.io/MRSm4F.jpg)
By leveraging this query, managers can improve customer retention and enhance the overall shopping experience. Tracking individual purchase patterns also helps in tailoring marketing efforts, such as sending targeted discounts or special offers to frequent customers.

2. Query #2 retrieves all orders that are still pending and have not yet been processed. It helps bakery managers and staff stay on top of order fulfillment, ensuring that pending orders are prioritized to minimize delays and maintain customer satisfaction.
![App Screenshot](https://snipboard.io/nGplSr.jpg)
By identifying pending orders, managers can allocate resources efficiently, streamline workflow, and prevent backlogs. This is essential for maintaining smooth operations, optimizing inventory management, and delivering timely service to customers.

3. Query #3 retrieves the names and contact information of customers who have made at least one purchase. It helps bakery managers identify active customers, allowing them to engage with their customer base through marketing campaigns, loyalty programs, and personalized follow-ups.
![App Screenshot](https://snipboard.io/l0Lxth.jpg)
By using this query, managers can strengthen customer relationships, encourage repeat purchases, and enhance retention strategies. It also enables targeted promotions, such as exclusive discounts for frequent buyers or re-engagement offers for past customers.

4. Query #4 retrieves the names and contact information of customers whose names begin with the letters 'A' or 'B'. It allows bakery managers to segment their customer base for targeted promotions, personalized marketing campaigns, or special loyalty programs.
![App Screenshot](https://snipboard.io/9kRn6A.jpg)
By utilizing this query, managers can create exclusive offers for specific customer groups, send personalized messages, and enhance customer engagement. This segmentation strategy helps improve marketing effectiveness and build stronger customer relationships.

### Complex Queries: 

5. Query #5 retrieves details on which employees handled specific customer orders. It helps bakery managers ensure accountability, balance workload distribution, and improve customer relationship management by tracking repeat customers and analyzing order trends.
![App Screenshot](https://snipboard.io/1iVEkZ.jpg)
By using this query, managers can monitor employee performance, recognize top performers, and identify areas for improvement. Additionally, it enables personalized service by linking employees with frequent customers, fostering stronger customer relationships.

6. Query #6 retrieves details on which employees handled specific customer orders, helping bakery managers ensure accountability, balance workload distribution, and improve customer relationship management by tracking repeat customers and analyzing order trends. Tracking order trends can help optimize staffing decisions, ensuring employees are efficiently allocated based on demand.
![App Screenshot](https://snipboard.io/EZSo8l.jpg)
By using this query, managers can monitor employee performance, recognize top performers, and identify areas for improvement. Additionally, it enables personalized service by linking employees with frequent customers, fostering stronger relationships, and ensuring a high level of service. 

7. Query #7 calculates the total revenue generated by each product, allowing bakery managers to identify best-selling items and underperforming products. It aids in inventory planning, pricing strategies, and promotional decisions to maximize profitability.
![App Screenshot](https://snipboard.io/qjTiAe.jpg)
By analyzing product revenue, managers can optimize stock levels, adjust pricing for maximum profit, and run targeted promotions on slow-moving items. This data-driven approach enhances overall business efficiency and customer satisfaction.

8. Query #8 retrieves the names of products that have never been purchased. It helps bakery managers recognize low-demand or overlooked items, allowing them to adjust inventory, refine the product lineup, or run targeted promotions to boost sales.
![App Screenshot](https://snipboard.io/sgxG4S.jpg)
By using this query, managers can make data-driven decisions to either phase out unpopular products, bundle them with best-sellers, or offer discounts to encourage sales, ultimately improving overall business performance.

9. Query #9 retrieves the suppliers that provide the highest number of ingredients to the bakery, helping managers understand which suppliers are key to their inventory. It aids in optimizing supplier relationships, negotiating better deals, ensuring a stable supply chain, and preventing over-reliance on a single supplier.
![App Screenshot](https://snipboard.io/32cOGx.jpg)
By using this query, managers can make informed decisions about supplier performance, prioritize negotiations with high-volume suppliers, and ensure the bakery is not vulnerable to disruptions in the supply chain.

10. Query #10 identifies the most ordered product and the total quantity sold, helping bakery managers understand which product drives the highest demand. This insight informs inventory planning, marketing strategies, and potential pricing adjustments to boost profitability and customer satisfaction.
![App Screenshot](https://snipboard.io/oIY4uZ.jpg)
By leveraging this data, managers can optimize stock levels for the most popular items, plan targeted promotions, and adjust pricing to maximize sales and ensure consistent product availability.
## Database Information: 
### Name of the database: 
al_Group_47114_G6



