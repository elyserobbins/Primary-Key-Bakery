# **Primary-Key-Bakery**

## **Team 6 - MIST 4610 Group Project 1**

### **Team Name:**  
MIST4610.47114.20254 Spring 2025 SEC - 6  

### **Team Members:**  
- **Luke Eckert** - [@Luke-Eckert](https://github.com/Luke-Eckert)  
- **Elyse Robbins** - [@elyserobbins](https://github.com/elyserobbins)  
- **Claire Lee** - [@clairerlee](https://github.com/clairerlee)  
- **Elliot Wallace** - [@e8w-9837](https://github.com/e8w-9837)  

---

## **Problem Description**
The task at hand is to model and build a relational database for the general workings of a bakery business. The central entity in the model is the **Bakery** entity, representing each physical bakery location that the company owns and operates in various areas. 

The bakery operates in conjunction with the **products** it sells, the **ingredients** it sources, the **suppliers** it works with, and the **customers** who purchase from them, whether in-store or via special orders.

We are interested in accurately modeling these relationships, generating sample data, and populating the entities and their attributes with this sample data. Furthermore, we will perform **functional queries** to provide valuable business insights about the bakery’s operations, such as:
- Tracking **best-selling products**
- Monitoring **ingredient inventory**
- Evaluating **supplier reliability**
- Analyzing **customer purchasing trends**

---

## **Data Model**
   First off, the supplier entity represents the different vendors from which our bakery gets its raw materials. Within this entity, we have the primary key (supplierID), as well as the name of supplier, their contact info, and information about the product that they provide. Suppliers can provide multiple ingredients. Each ingredient is identified by a unique IngredientsID and has a name, a reference to its supplier (foreign key), a quantity, a cost per unit, and an expiration date.
   
   Ingredients and Products have a many to many relationship - connected by a table named “Products_Ingredients”. The Products entity contains all items that are available for sale in the bakery, which includes attributes such as the Name, Category, Price, and Availability of the product. In the Product_Ingredients entity there are two foreign keys pulled from Products (ProductID) and Ingredients (IngredientID), as well as the attribute Quantity required for making each product.  
   
   The Customers table maintains records of customer details such as names, contact information, and loyalty program status. Customers place Orders, forming a one-to-many relationship where a customer can have multiple orders. The Orders entity contains order-specific details such as order date, total cost, and order status. Since each order consists of multiple products, we introduce the Order_Items table, which links Orders to Products in a many-to-many relationship. This table tracks the quantity of each product in an order and its subtotal.
   
   The Products entity also has a many to many relationship with the Orders entity, connected by the associative entity Order_Items. Within the Order_Items table, there is its own primary key (OrderItemID), as well as two forging keys that are pulled from the Orders entity and the Products entity. Regarding the attributes in the Order_Items table, there is the quantity of the items in the order, as well as the subtotal of the order. Regarding the Orders entity, it has its own primary key (OrderID), as well as a foreign key from the Customers table. Regarding its own attributes not related to other tables, the OrderDate, OrderStatus, and TotalCost of the order is also tracked within the Orders table. Related to the Orders entity is the Customers entity, as one customer can have many orders. Within the Customers entity, there is a primary key (CustomerID), as well as the name of the customer, contact information, and the customer's status within the bakery’s loyalty program.
   
   The Employees table records bakery staff details, including their names, roles, salaries, and work schedules. Employees are assigned to specific tasks via the Employee_Assignments table, which tracks the task description and assignment dates. Employees also play a role in fulfilling orders, which is represented by the Employees_Orders table. This entity captures which employees are responsible for each order and their roles in the process (e.g., cashier, baker, delivery).

---

## **Data Dictionary**

| **Table Name**        | **Description** |
|----------------------|----------------|
| **Customers**       | Stores customer details and loyalty information |
| **Employees**       | Tracks bakery staff roles, salaries, and schedules |
| **Employee_Orders** | Links employees to the orders they handle |
| **Employee_Assignments** | Tracks tasks assigned to employees |
| **Ingredients**     | Stores raw ingredients data and suppliers |
| **Order_Items**     | Links orders to products and tracks quantities |
| **Orders**         | Records customer purchases and order statuses |
| **Product_Ingredients** | Links products to their ingredients |
| **Products**       | Stores all bakery products for sale |
| **Suppliers**      | Stores supplier details and ingredients provided |

---

## **Queries**

### **Simple Queries**
1. **Retrieve all orders placed by a specific customer (CustomerID = 1010).**
   - Helps track customer purchase history and analyze buying habits.

2. **Retrieve all orders that are still pending and have not yet been processed.**
   - Helps bakery managers prioritize order fulfillment.

3. **Retrieve names and contact information of customers who have made at least one purchase.**
   - Identifies active customers for loyalty programs.

4. **Retrieve names and contact information of customers whose names begin with 'A' or 'B'.**
   - Segments customers for targeted marketing campaigns.

### **Complex Queries**
5. **Retrieve details on which employees handled specific customer orders.**
   - Ensures accountability and workload balance.

6. **Calculate total revenue generated by each product.**
   - Helps identify best-selling and underperforming items.

7. **Retrieve products that have never been purchased.**
   - Helps managers refine inventory and promotions.

8. **Retrieve suppliers providing the highest number of ingredients.**
   - Optimizes supplier relationships and supply chain management.

9. **Identify the most ordered product and total quantity sold.**
   - Helps inform inventory planning and pricing strategies.

---

## **Database Information**
**Database Name:** `al_Group_47114_G6`

---

## **Additional Resources**
- **Image Hosting:** [Snipboard](https://snipboard.io/)
- **GitHub Profile Links:**
  - [Elyse Robbins](https://github.com/elyserobbins)
  - [Luke Eckert](https://github.com/Luke-Eckert)
  - [Claire Lee](https://github.com/clairerlee)
  - [Elliot Wallace](https://github.com/e8w-9837)
