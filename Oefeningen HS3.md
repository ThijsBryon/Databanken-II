# Oefeningen hoofdstuk 3 SQL Advanced
```sql
-- Oefening 1 (klopt nog niet)

select o.OrderID, p.ProductName  
from Orders o JOIN OrdersDetail r RIGHT JOIN Product p
ON  o.OrderID = r.OrderID
ON r.ProductID=p.ProductID
EXCEPT 
SELECT productid FROM ordersdetail



-- Oefening 4
SELECT OrderID 
FROM Orders o
WHERE OrderAmount <> 
(
	SELECT SUM(quantity * UnitPrice)
	FROM OrdersDetail od
	WHERE od.OrderID = o.OrderID
)


-- Oefening 7
SELECT  PLAYERNO, NAME
FROM PLAYERS p
WHERE (
	SELECT COUNT(PAYMENTNO)
	FROM PENALTIES pe
	WHERE pe.PLAYERNO = p.PLAYERNO
	) 
	>
	(
	SELECT COUNT(MATCHNO)
	FROM MATCHES m
	WHERE m.PLAYERNO = p.PLAYERNO
	)

-- Oefening 
```