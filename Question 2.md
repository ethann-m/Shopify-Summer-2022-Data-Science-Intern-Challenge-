# Question 2

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
