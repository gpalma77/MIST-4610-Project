# MIST 4610: Team 7 Group Project 1 

## Team Name 
Team 7
<br>  
## Team Members
Giovanna Palma - [@gpalma77](https://github.com/gpalma77/MIST-4610-Project
)
<br> 
Katie Witcher - [@katiewitcher](https://github.com/katiewitcher/Coffee)
<br> 
Jack Macken- [@jackmacken](https://github.com/jackmacken/4610Project)
<br> 
Andrew Baich - [@andrewbaich](https://github.com/AndrewBaich/MIST-4610-Team-7)
<br> 
Brooke Istishin - [@brookeistishin](https://github.com/brookeistishin/MIST4610GroupProject1
) 
<br> 
## Scenario description:
Our project models a small, local coffee shop chain in Georgia, operating multiple locations under unique names, but all managed centrally with a unified menu. The owner oversees all locations using a central data center to streamline operations.
Key entities in the database include Customer, Order, Employee, Coffee Shop, OrderItem, MenuItem, RecipeItem, Ingredients, Supplier, and Category. These entities and their relationships allow the database to efficiently track customer visits, the details of their orders, payment methods, and the employee handling each transaction at a specific location. Additionally, the database stores information on the menu items ordered, their ingredients, and the corresponding recipes. It also manages stock levels and tracks suppliers for each ingredient, ensuring a seamless supply chain.

## Data Model:
   Each customer is uniquely identified and can place multiple orders over time. There is a one-to-many relationship between the Customer and Order entities, meaning that a customer can make many orders, but an order is linked to only one customer. <br> 
  Orders capture the details of a customer’s purchase, including the date of the order and the total amount. Each order is associated with one customer and one employee, reflecting that the order is processed by a specific employee at a given coffee shop. However, each employee can handle multiple orders, creating a one-to-many relationship between the Employee and Order entities.<br> 
  Employees are linked to a specific coffee shop location and are responsible for handling customer orders. There is a one-to-many relationship between the CoffeeShop and Employee entities, indicating that a coffee shop can have multiple employees, but each employee works at only one coffee shop. Additionally, each employee has a boss, represented by a one-to-many recursive relationship where one employee can manage several others.<br> 
  Each coffee shop location is uniquely identified and operates under a unified menu system. There are five coffee shops: Witcher Brew, Andrew's Affogato, Brooke Beanery, Gio's Grind House, and Macken Macchiato. Coffee Shop has a one-to-one relationship with the Employee entity as one employee is the boss of one store, and each store only has one employee as the boss (store manager).Coffee Shop also has a one-to-many relationship with the Ingredients entity as a coffee shop can hold inventory of multiple ingredients but a specific ingredient is only held at one store. <br> 
  Orders often contain multiple menu items, such as different types of coffees or pastries. The OrderItem entity acts as a weak entity between Order and MenuItem, capturing the details of which menu items were included in each order and in what quantity. An order can contain many menu items, and a menu item can be included in multiple orders, making OrderItem an associative entity.<br> 
Menu items represent the products sold by the coffee shops, such as different types of drinks or food. Each menu item belongs to one category, such as "Breakfast”.. There is a one-to-many relationship between the     
  Category and MenuItem entities, meaning that a category can contain many menu items, but a menu item belongs to only one category.<br> 
  The RecipeItem entity details the ingredients required to create each menu item. A single menu item can require multiple ingredients, such as coffee, sugar, or milk, while the same ingredient can be used in many different menu items. This is represented by the many-to-many relationship between MenuItem and Ingredient.
  Ingredients represent the raw materials needed to prepare menu items. There is a one-to-many relationship between the Supplier and Ingredient entities, meaning that a supplier can provide multiple ingredients, but each ingredient is sourced from only one supplier.<br> 
  Suppliers provide the ingredients required to prepare the coffee shop’s menu items. Each supplier can supply multiple ingredients to different coffee shop locations, ensuring a steady flow of stock to maintain operations.<br> 

 
![image](https://github.com/user-attachments/assets/7dae2bbe-61ec-43e4-acee-34c9a6dd56cc)


 
## Data Dictionary:
<img width="468" alt="image" src="https://github.com/user-attachments/assets/40f72c6c-890b-47a8-924e-e290f165783d">
<br>
<img width="468" alt="image" src="https://github.com/user-attachments/assets/c7a28666-8024-471a-b94a-38e19fa23bc0">
<br>
<img width="468" alt="image" src="https://github.com/user-attachments/assets/11d7c1c3-b604-4452-b227-00fb19ed9ade">
<br>
<img width="487" alt="image" src="https://github.com/user-attachments/assets/2cf23f36-e130-416a-a85c-cda279feb94d">
<br>
<img width="468" alt="image" src="https://github.com/user-attachments/assets/7edd0220-fab8-498e-9540-2ec312f5ec89">
<br>
<img width="468" alt="image" src="https://github.com/user-attachments/assets/25dbb014-50b7-4cc6-b691-ddb403f90220">
<br>
<img width="468" alt="image" src="https://github.com/user-attachments/assets/9df74cf8-1db0-42c6-82b6-251f20c55110">
<br>
<img width="468" alt="image" src="https://github.com/user-attachments/assets/9b3c92af-3378-4b51-b88c-37a2e40fd951">
<br>
<img width="468" alt="image" src="https://github.com/user-attachments/assets/4d6b70f4-b172-4320-ba9d-b85a2978e144">
<br>
<img width="468" alt="image" src="https://github.com/user-attachments/assets/04126216-4097-4a41-a36f-70abe0aaf2ce">
<br>

 
## TEN QUERIES:
 <img width="466" alt="image" src="https://github.com/user-attachments/assets/6b5d2034-aaf4-4111-9310-c09bf99dde96">
<br>



1. Query 1 finds the most frequently ordered menu items by counting the occurrences of each menu item in the ‘OrderItem’ table. The results are also ordered by the number of occurrences of each menu item in descending order. 
![image](https://github.com/user-attachments/assets/0de2fb8c-a0ed-4951-9cb8-80cceda6b899)


Query 1 allows managers to track what menu items are the most popular and see which ones are not selling well.  This is important for optimizing inventory levels to make sure the right amount of items are stocked. It can also help management make important decisions when designing or updating the menu to ensure customer satisfaction and further sales. Additionally, it will help management focus marketing and promotion efforts on popular items. Listing the results in descending order helps with efficiency when retrieving information about which menu items to promote and stock the most of.    
<br>
<br>


2. Query 2 retrieves the employees who have processed more than 3 orders. It then organizes the number of orders each employee has processed in descending order. 
![image](https://github.com/user-attachments/assets/d5f19f8c-c5ef-44e2-ad57-40754068ac48)


Query 2 allows managers to see employee performance on handling orders. This is important for understanding employee efficiency, time management, and overall employee performance. Managers can use this information for future schedules in order to optimize employee productivity and work distribution. This information can also help with goal and target setting for employees to motivate them. 
<br>
<br>


3. Query 3 counts the frequency of each payment type, either credit, cash, or debit. It also orders the results by descending frequency. 
![image](https://github.com/user-attachments/assets/5840feee-b9d0-4be3-81ef-6813354b02d5)


Query 3 allows managers to understand customer preferences and which payment options to promote or expand. For instance, if the manager wanted to decide if the establishment should be accepted. Different payment methods can also come with varying fees (credit fees on transactions, etc.) which can help managers understand the most cost-effective methods to use. This can lead to managers potentially negotiating better rates or finding cost-saving opportunities. 
<br>
<br>

  
4. Query 4 reports the total amount of all cash orders. 
  ![image](https://github.com/user-attachments/assets/34970c70-421c-443e-99ea-3f3e1107f6b1)


Query 4 allows managers to have an immediate snapshot of the business’s daily revenue to help understand the company’s financial health. Having information about the business’s cash flow helps to ensure the business is functioning at optimal liquidity to cover expenses. It also helps managers to evaluate if sales goals are being met and identify if the business has a steady cash flow. 
<br>
<br> 

 
5. Query 5 retrieves all ingredients where the quantity in stock is less than 30 at the location. 
![image](https://github.com/user-attachments/assets/cf2a9aa4-d40b-4eef-a367-5962d352f4b4)


Query 5 allows managers to maintain efficient inventory management by monitoring low stock levels. This will allow for optimal inventory levels and ensure that there is enough stock of ingredients for the items without over-ordering. Managers will be able to better meet customer demand and avoid loss of business. Knowing the low stock quantity will also aid cost control, helping managers reorder ingredients at the most optimal time and plan ahead while minimizing waste. 
<br>
<br> 

   
6. Query 6 selects the average total sales from each category of menu items. 
![image](https://github.com/user-attachments/assets/54870154-10a8-4f3e-bba8-064aa2219e77)


Query 6 allows managers to understand total sales by category, helping them grasp which product categories are contributing most to revenue. By comparing these sales figures with associated costs, the coffee shop could find out which categories (e.g., coffee, pastries, etc.) offer the highest profitability. This may allow for a variety of things - like optimizing pricing, managing inventory more efficiently, and focusing promotional efforts on the best categories.
<br>
<br> 

   
7. Query 7 shows how many employees each boss is responsible for managing. 
 ![image](https://github.com/user-attachments/assets/34cf6cf1-6a4d-4332-a2de-c58976abb8ac)


Query 7 can help the coffee shop when evaluating effective management and workload distribution. By tracking the number of employees reporting to each boss, they can balance team sizes, prevent overburdening managers, and identify areas where additional leadership may be needed. 
<br>
<br> 


8. Query 8 reports each supplier name that supplies more ingredients than the average amount of ingredients that each supplier supplies.
![image](https://github.com/user-attachments/assets/3b0e20ec-15d2-4d96-bfa2-85358df3d0f7)

Query 8 allows managers to track how much stock comes from each supplier with shows the reliability and performance of suppliers. This can help to hold suppliers accountable to their delivery schedules and order quantity requests. It also allows for managers to maintain optimal inventory levels by having a better understanding of how many recipes and menu items are reliant on which suppliers. If the business is too reliant on one supplier for its ingredients and that supplier has issues such as delays or supply shortages there could be increased risk. It is important for managers to diversify their supply chain to mitigate operational disruption. 
<br>
<br> 


9. Query 9 reports menu items that have not been ordered yet. (Items that appear in no Orders by checking OrderItems). 
  ![image](https://github.com/user-attachments/assets/852a7f77-b156-4a03-a964-ede9caf1d940)


Query 9 allows managers to track how many items are still available for purchase. This can help to quickly identify what items need to be restocked, allowing for better efficiency and inventory management efforts. It can also help managers to identify which menu items may be less popular, aiding menu design. 
<br>
<br> 
 

10. Query 10 reports the id of employees that have processed Criag’s order.
![image](https://github.com/user-attachments/assets/6ee9529f-9c63-4535-af9a-8f60b353eab7)


Query 10 allows managers to access information that would be helpful in the event that Craig (or another customer) reported a complaint or posted a bad review and management wanted to know which employees might be responsible for the negative customer experience. This can help managers hold employees accountable, complete employee evaluations, and improve customer service overall. 
<br>
<br> 
 
## Database information:
Name of database: cs_gcp90285

Additional information: Each Each query listed above is marked in the database using stored procedures which can be called using the following format: CALL TP_Q1();


