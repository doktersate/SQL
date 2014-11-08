SQL
===

NOTESS

Select the maximum price of any item ordered in the items_ordered table. Hint: Select the maximum price only.
  select max(price) from items_ordered;

Select the average price of all of the items ordered that were purchased in the month of Dec.
  select avg(price) from items_ordered where order_date like '%Dec%';

What are the total number of rows in the items_ordered table?
  select count(*) from items_ordered;

For all of the tents that were ordered in the items_ordered table, what is the price of the lowest tent? Hint: Your query should return the price only.
  select min(price) from items_ordered where item like 'Tent';
  
How many people are in each unique state in the customers table? Select the state and display the number of people in each. 
  select state, count(state) from customers group by state;

From the items_ordered table, select the item, maximum price, and minimum price for each specific item in the table. Hint: The items will need to be broken up into separate groups.
  select item, max(price), min(price) from items_ordered group by item;

How many orders did each customer make? Use the items_ordered table. Select the customerid, number of orders they made, and the sum of their orders. Click the Group By answers link below if you have any problems.
  select customerid, count(customerid), sum(price) from items_ordered group by customerid;
  
How many people are in each unique state in the customers table that have more than one person in the state? Select the state and display the number of how many pselect state, count(state) from customers group by state having count(state)>1;
  select state, count(state) from customers group by state having count(state)>1;

From the items_ordered table, select the item, maximum price, and minimum price for each specific item in the table. Only display the results if the maximum price for one of the items is greater than 190.00.
  select item, max(price), min(price) from items_ordered group by customerid having max(price) > 190.00;
  
How many orders did each customer make? Use the items_ordered table. Select the customerid, number of orders they made, and the sum of their orders if they purchased more than 1 item.
  select customerid, count(customerid), sum(price) from items_ordered group by customerid having count(customerid)>1;
  
Select the lastname, firstname, and city for all customers in the customers table. Display the results in Ascending Order based on the lastname.
  select lastname, firstname, city from customers order by lastname asc;
  select lastname, firstname, city from customers order by lastname desc;
  
Select the item and price for all of the items in the items_ordered table that the price is greater than 10.00. Display the results in Ascending order based on the price.
  select item, price from items_ordered where price > 10.00 order by price asc;
  
Select the customerid, order_date, and item from the items_ordered table for all items unless they are 'Snow Shoes' or if they are 'Ear Muffs'. Display the rows as long as they are not either of these two items.
  select customerid, order_date, item from items_ordered where item <> 'Snow Shoes' and item <> 'Ear Muffs';

Select the item and price of all items that start with the letters 'S', 'P', or 'F'.
  select item, price from items_ordered where (item like 'S%') or (item like 'P%') or (item like 'F%');

Select the date, item, and price from the items_ordered table for all of the rows that have a price value ranging from 10.00 to 80.00.
  select order_date, item, price from items_ordered where price between 10.00 and 80.00;
  
Select the firstname, city, and state from the customers table for all of the rows where the state value is either: Arizona, Washington, Oklahoma, Colorado, or Hawaii.
  select firstname, city, state from customers where state in ('Arizona' or 'Washington' or 'Oklahoma' or 'Colorado' or 'Hawaii');
  
Select the item and per unit price for each item in the items_ordered table. Hint: Divide the price by the quantity.
  select item, sum(price)/sum(quantity) from items_ordered group by item;
  
Write a query using a join to determine which items were ordered by each of the customers in the customers table. Select the customerid, firstname, lastname, order_date, item, and price for everything each customer purchased in the items_ordered table.
  select customers.customerid, customers.firstname, customers.lastname, items_ordered.order_date, items_ordered.item, items_ordered.price from customers, items_ordered where customers.customerid = items_ordered.customerid;
  
Repeat exercise #1, however display the results sorted by state in descending order.
  select customers.customerid, customers.firstname, customers.lastname, items_ordered.order_date, items_ordered.item, items_ordered. price from customers, items_ordered where customers.customerid = items_ordered.customerid order by customers.state desc;
  

