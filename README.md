# Group Project Chick-fil-a Data Model


## Group Repositories
Jonathan Troyer - https://github.com/jonathantroyer31/Group-Project-1

Carol Hubach - https://github.com/carolhubach/4610-Group-Project-1

Lena Dindayal - https://github.com/lenadindayal/4610-Group-Project-1

Lily Athey - https://github.com/lilyathey/MIST-4610-Project-1

Valerie Penaranda - https://github.com/valerieep/Group-Project1




## Problem Description

Chick-fil-A is a fast-food restaurant chain that specializes in chicken sandwiches, nuggets, biscuits, and other chicken-based dishes. Chick-fil-A allows franchisees to own and operate a Chick-fil-A restaurant which is depicted by a restaurant location. Owners can franchise one restaurant or multiple and each restaurant has their own operations and employees. The locations have the same menu which comes down from Chick-fil-A headquarters. As any fast food operation, Chick-fil-A has a menu filled with items that customers can order from. Additionally, Chick-fil-A has ingredients which are used in making the food the restaurant sells. Chick-fil-A has employees who have shifts as well because the employees help run operations through cooking, taking orders, cleaning, doing dishes, etc. Chick-fil-A also has customers who have loyalty accounts so they can obtain rewards, among other things. Overall, Chick-fil-A's business operation prioritizes high-quality food made with fresh ingredients and exceptional customer service. Corporate also emphasizes the importance of franchise partnerships and fostering the mission and vision of the company. 
## Data Model

![image](https://user-images.githubusercontent.com/128402127/229163316-4191a7b8-0901-48f2-b128-c67e94afadb5.png)


The owner of the Athens Chick-fil-A franchise location has three branches: Downtown, Beechwood, and Atlanta Highway. These locations have many employees. An employee can manage many people but an employee can only be managed by one person so a recursive one to many relationship exists. Employees have many shifts and shifts can have many employees. The associative entity ShiftDetails that is present between Employees and Shifts has additional attributes like clock in date and time and clock out date and time. This is an identifying many-to-many relationship. 

Employees can work on many orders. Customers place many orders. We have a one to one relationship between customer and loyalty as a customer can have one loyalty account and vice versa. Orders and Menu Items have a many to many relationship where an order can have multiple menu items and a menu item can be in multiple orders. The associative entity between the two is Order Details which has additional attributes like item quantity and order time. Menu items and ingredients have a many to many relationship as menu items have many ingredients and an ingredient can be in multiple menu items. The ensuing associative entity is menuItemDetails.

Each location has a unique identification number, location name, address, and phone number. 
Each employee has a unique identification number, first name, last name, phone number, address, email, and position. Each shift has a unique identification number, shift start time, and shift end time. Each customer has a unique identification number, first name, last name, phone number, address, and email. The loyalty table has a unique identification number, loyalty status, loyalty points, and date joined. Each order has an order number, type, and status. Each menu item has a unique identification number, a name, price, description, and an attribute for if it is in stock. Each ingredient has a unique identification number, a name, price, and quantity. 

## Augmented Data Model
After looking at our data model, we came to the conclusion that we could augment it by adding a Promotions table. Athens CFA locations have many promotions. For instance, the Beechwood location does Bingo night. In addition, specific CFAs send out rewards to their customers. In order to represent this, we created the entity Promotion. The primary key is promID and the other attributes are promoType (for promotion type), promoDate (for promotion date), promoCost (for promotion cost). We created a many to many relationship between Location and Promotion since many locations have promotions and promotions can be present in many locations. The associative entity between Location and Promotion is PromotionDetails. Promotion Details has an identifying relationship between Promotion and Location. Apart from these changes, the model remains the same.

## Data Dictionary
The data dictionary file shows the columns for each table which includes the name of the column, the descption, the type of data, the size of the data, the format of the data, and if the data is a primary or foreign key. 
![image](https://user-images.githubusercontent.com/128402127/229163829-b647b3cb-d050-419a-b43d-bb07b0a8c885.png)
![image](https://user-images.githubusercontent.com/128402127/229165999-04706db4-d022-43a0-9e22-dd5e4abde58c.png)
![image](https://user-images.githubusercontent.com/128402127/229164173-a1183058-977d-42be-a0a8-9fe3cde86671.png)
![image](https://user-images.githubusercontent.com/128402127/229165148-e93e7349-4ff2-4beb-ab71-8b877444c104.png)
![image](https://user-images.githubusercontent.com/128402127/229165416-cbf5968b-ad73-46a3-a2d9-d74ebf4470c2.png)
![image](https://user-images.githubusercontent.com/128402127/229165598-b97e5965-a0fb-411a-ae83-fdc149bcfc51.png)
![image](https://user-images.githubusercontent.com/128402127/229165680-2b70cf78-4ef2-49f5-ab56-a6c60fe7fbd1.png)
![image](https://user-images.githubusercontent.com/128402127/229167125-b005b724-cd94-4b85-97ae-6ea3ab631053.png)
![image](https://user-images.githubusercontent.com/128402127/229168018-b4f43fc1-cf7a-43e4-8460-b15cae4df073.png)
![image](https://user-images.githubusercontent.com/128402127/229168115-3a15e64e-754a-4b93-b193-cc593f8ef881.png)
![image](https://user-images.githubusercontent.com/128402127/229168211-a36d3071-8dc1-4f6f-a639-3b0b6c812e53.png)
![image](https://user-images.githubusercontent.com/128402127/229168401-b8a278e8-bb2c-475f-8529-1a156baefb55.png)
![image](https://user-images.githubusercontent.com/128402127/229168472-f1a20147-a96e-4780-aec0-c921aa2286f9.png)

## Queries
#1

 ![image](https://user-images.githubusercontent.com/128402127/229170076-37bfc691-97cd-4f84-96ca-e4e16aa1c0cf.png)

Description: What customers have a Signature loyalty status?

Justification: This query will allow the store owners and managers to acquire a list of their most loyal and frequent customers. The Signature status and loyalty program in general allow CFA to create an ongoing relationship with their frequent customers. This list can specifically be used to send out surprise rewards to customers with Signature status only which is something that CFA currently does.

#2

 ![image](https://user-images.githubusercontent.com/128402127/229170131-bedcd1bf-c23b-4827-9551-55aa0d25d9ea.png)

Description: How many Red status loyalty members do we have?

Justification: This query will create a promotional list where the CFA team can send a promotional email to these customers who have loyalty accounts and are already frequent customers that are one step down from the “Signature” loyalty status which is the highest level. Managers will want to see how many customers they have that are still frequent and that can hopefully be bumped up to the highest status.

#3

 ![image](https://user-images.githubusercontent.com/128402127/229174239-6fbff475-8c9d-4251-898f-efafbc70315c.png)

Description: How many employees have taken more than 3 orders?
Justification: This will give the manager insight into whether or not their employees are doing their job by keeping track of the orders they took.

#4

 ![image](https://user-images.githubusercontent.com/128402127/229174280-1bbaf95d-1c2e-4f92-8d29-bbe6c0f750a3.png)

Description: How many employees worked on April 17th, 2022?

Justification: If there were to be an incident on a specific day, the manager could look at who was working that day to ask the employees that worked that day for more information. 

#5
 
 ![image](https://user-images.githubusercontent.com/128402127/229174320-72103fe4-458a-4b28-a3d9-fa04eca4e928.png)

Description: Which employees have not worked in 5 months?

Justification: A manager would be interested in obtaining a list of employees who have not worked in five months to see if these employees should still be on the payroll. If employees have not worked in five months, they may no longer want to work and the manager needs to know this to make staffing decisions and for budget considerations.

#6
 
 ![image](https://user-images.githubusercontent.com/128402127/229174358-2fa70bae-1d3d-4630-882f-07e6148d61eb.png)

Description: What percentage of customers have ordered a kids meal?

Justification: A manager would be interested in obtaining the percentage of customers who have ordered a kids meal because this statistic will impact menu planning, inventory management, and cost management. For menu planning, if a lot of customers order kids meals, the owner can get feedback about what menu items are popular and what changes can be made.

#7
 
 ![image](https://user-images.githubusercontent.com/128402127/229174378-4f5ffcd2-1a00-43f9-8816-f8d68e9fc324.png)

Description: Which menu items have orders in which the quantity of item ordered is greater than the average quantity for that item?

Justification: A manager would be interested in obtaining the amount of orders that have a larger quantity than the average amount in order so that they are able to forecast sales and maintain inventory management. By understanding which menu items are ordered in larger quantities, they can adjust inventory levels and fulfill all orders while balancing the cost of ordering inventory. 

#8
 
 ![image](https://user-images.githubusercontent.com/128402127/229174402-039207cf-a2e5-4a8f-9342-6d9867c2e6d2.png)

Description: What is average order size and the amount of employees working on orders during lunch hour (12 - 2)?

Justification: A manager would be interested in the average order size and number of employees that worked during the lunch rush because results would influence how shifts are staffed. If the average indicates that there are many large orders during a specific time, a manager would schedule more employees to reflect the busy nature of the restaurant and vice versa. 

#9
 
![image](https://user-images.githubusercontent.com/128402127/229175863-fc964d9a-ab71-4413-82cb-ec6a0ac9c432.png)

Description: How many products of each type are left in inventory at the beechwood location?

Justification: The managers of the store must know how much inventory they currently have. This is extremely important to know because it determines when to order more products and how much to purchase. Chick-fil-a is known for its reliability so it is vital that everything is in stock and delivered on time. 

#10
 
![image](https://user-images.githubusercontent.com/128402127/229175938-28bcdda7-7d8a-4281-8ad6-cba884dc5a01.png)

Description: Which location has sold the most amount of Mac and Cheese?

Justification: The manager must know which location has sold the most of a certain item because he or she will be able to see which location has the highest profitability. This is important because if one location is struggling at selling the item, this may show that they are preparing the item wrong, not marketing correctly, or having some other kinds of issues. By having the data to see which location is excelling with this item, the others can learn from it and overall profitability can increase. 


## Query Matrix

![image](https://user-images.githubusercontent.com/128402127/229176030-c4058008-3445-4a38-9fa1-8abc2472abf3.png)

The query matrix provides a description of the complexity of each query which includes multiple table joins, subqueries, correlated subqueries, REGEXP, built-in function, calculated fields, where, not exists, group by, having, and order by. 




