# ODI Parameter

## Target Report

[Example](http://oz.ozeform.io/oz/edu/reportdev/order-odiparam.html)

## Create order-odiparam.odi

Copy **`order.odi`** to **`order-odiparam.odi`**.

#### 1. Add ODI parameter

1. Go to the **Data** window
2. Right-click **USER-DEFINED PARAMETER**
3. Select **Add Parameter Field**
4. Add an ODI parameter "**orderID**" to the member pane.

#### 2. Update Query

1. Add WHERE clause with ODI parameter

```sql
-- order
SELECT orderheader.SalesOrderID, customer.Channel, customer.CustomerName, orderheader.DueDate, orderheader.ShipDate, orderheader.TotalDue, customer.EmailAddress, customer.Phone, address.PostalCode, address.Country, address.StateProvince, address.City, address.AddressLine1, orderheader.PurchaseOrderNumber 
FROM orderheader 
INNER JOIN customer ON customer.CustomerID = orderheader.CustomerID
INNER JOIN address ON address.AddressID = orderheader.AddressID
WHERE orderheader.SalesOrderID = #OZParam.orderID#
ORDER BY address.Country ASC, address.StateProvince ASC, address.City ASC, customer.CustomerName ASC, orderheader.SalesOrderID ASC
```

You can run the query by providing a value for the parameter orderID \(for example, 63222\).

## Create order-odiparam.ozr

Copy **`order-detail.ozr`** to **`order-odiparam.ozr`**.

**1. Put the parameter value**

1. Datainfo &gt; DataTree &gt; order &gt; OZParam &gt; Select order ID
2. Properties &gt; Data &gt; set Field Value to "63222".
3. Preview

#### 2. Set the ParameterToolbar

1. Components &gt; right click ParameterToolbar &gt; Refresh Toolbar Wizard
2.  Move order.orderID to the Selected parameter from the Selectable Parameter.
3. Set options as below.

![](../.gitbook/assets/image%20%286%29.png)

Preview the report. You can try a new value for **order ID**. \(ex: "69550"\)

![](../.gitbook/assets/image%20%281%29.png)

