# Group-Project1 

# Problem Description:
Chick-fil-A is a fast-food restaurant chain that specializes in chicken sandwiches, nuggets, biscuits, and other chicken-based dishes. Chick-fil-A allows franchisees to own and operate a Chick-fil-A restaurant which is depicted by a restaurant location. Owners can franchise one restaurant or multiple and each restaurant has their own operations and employees. The locations have the same menu which comes down from Chick-fil-A headquarters. As any fast food operation, Chick-fil-A has a menu filled with items that customers can order from. Additionally, Chick-fil-A has ingredients which are used in making the food the restaurant sells. Chick-fil-A has employees who have shifts as well because the employees help run operations through cooking, taking orders, cleaning, doing dishes, etc. Chick-fil-A also has customers who have loyalty accounts so they can obtain rewards, among other things. Overall, Chick-fil-A's business operation prioritizes high-quality food made with fresh ingredients and exceptional customer service. Corporate also emphasizes the importance of franchise partnerships and fostering the mission and vision of the company. 

# Data Model:

# Data Model Description: 
The owner of the Athens Chick-fil-A franchise location has three branches: Downtown, Beechwood, and Atlanta Highway. These locations have many employees. An employee can manage many people but an employee can only be managed by one person so a recursive one to many relationship exists. Employees have many shifts and shifts can have many employees. The associative entity ShiftDetails that is present between Employees and Shifts has additional attributes like clock in date and time and clock out date and time. This is an identifying many-to-many relationship. 

Employees can work on many orders. Customers place many orders. We have a one to one relationship between customer and loyalty as a customer can have one loyalty account and 
vice versa. Orders and Menu Items have a many to many relationship where an order can have multiple menu items and a menu item can be in multiple orders. The associative entity between the two is Order Details which has additional attributes like item quantity and order time. Menu items and ingredients have a many to many relationship as menu items have many ingredients and an ingredient can be in multiple menu items. The ensuing associative entity is menuItemDetails.

Each location has a unique identification number, location name, address, and phone number. 
Each employee has a unique identification number, first name, last name, phone number, address, email, and position. Each shift has a unique identification number, shift start time, and shift end time. Each customer has a unique identification number, first name, last name, phone number, address, and email. The loyalty table has a unique identification number, loyalty status, loyalty points, and date joined. Each order has an order number, type, and status. Each menu item has a unique identification number, a name, price, description, and an attribute for if it is in stock. Each ingredient has a unique identification number, a name, price, and quantity. 

# Augmented Data Model:

# Change in Data Model:
After looking at our data model, we came to the conclusion that we could augment it by adding a Promotions table. Athens CFA locations have many promotions. For instance, the Beechwood location does Bingo night. In addition, specific CFAs send out rewards to their customers. In order to represent this, we created the entity Promotion. The primary key is promID and the other attributes are promoType (for promotion type), promoDate (for promotion date), promoCost (for promotion cost). We created a many to many relationship between Location and Promotion since many locations have promotions and promotions can be present in many locations. The associative entity between Location and Promotion is PromotionDetails. Promotion Details has an identifying relationship between Promotion and Location. Apart from these changes, the model remains the same.

