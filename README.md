# Shopify-Summer-2022-Data-Science-Intern-Challenge-

Question 1

a. For this calculation, the AOV is being calculated, which leads to $3145.13. This is not a good metric to record, as there are some orders which contain a large number of shoes, which leads to the AOV being greater. A better way to evaluate the data is to calculate the average item value

b. For this data set, I will report the average item value (AIV), which is the cost of each order divided by the number of items in the order.

c. The AIV comes out to $357.92

Question 2

a.

SELECT COUNT(OrderID)

FROM [Orders]

JOIN [Shippers]

ON Orders.ShipperID = Shippers.ShipperID AND Shippers.ShipperName = "Speedy Express" ;


54 orders were shipped by Speedy Express.

b.

SELECT Employees.LastName

FROM [Employees]

JOIN [Orders]

WHERE Employees.EmployeeID = Orders.EmployeeID

GROUP BY Employees.LastName

ORDER BY COUNT(Orders.OrderID) DESC

LIMIT 1;


Peacock is the last name of the employee with the most orders.

 c.
 
SELECT Products.ProductName

FROM [Orders]

JOIN Customers, OrderDetails, Products

WHERE Orders.CustomerID = Customers.CustomerID AND Orders.OrderID = OrderDetails.OrderID AND Products.ProductID = OrderDetails.ProductID AND Country = "Germany"

GROUP BY Products.ProductID

ORDER BY Count(Products.ProductID) DESC

LIMIT 1;


Gorgonzola Telino was ordered most by customers in Germany.
