# Parámetro ODI

## Reporte Modelo

[Example](http://oz.ozeform.io/oz/edu/reportdev/order-odiparam.html)

## Create order-odiparam.odi

Copie **`order.odi`** a **`order-odiparam.odi`**.

#### 1. Añadiendo un parámetro ODI

1. Vaya a la ventana **Data**
2. Click-derecho en **USER-DEFINED PARAMETER**
3. Seleccione **Add Parameter Field**
4. Añada un parámetro ODI "**orderID**" al panel miembro.

#### 2. Actualizando la Query

1. Añada una orden WHERE con el parámetro ODI creado.

```sql
-- order
SELECT orderheader.SalesOrderID, customer.Channel, customer.CustomerName, orderheader.DueDate, orderheader.ShipDate, orderheader.TotalDue, customer.EmailAddress, customer.Phone, address.PostalCode, address.Country, address.StateProvince, address.City, address.AddressLine1, orderheader.PurchaseOrderNumber 
FROM orderheader 
INNER JOIN customer ON customer.CustomerID = orderheader.CustomerID
INNER JOIN address ON address.AddressID = orderheader.AddressID
WHERE orderheader.SalesOrderID = #OZParam.orderID#
ORDER BY address.Country ASC, address.StateProvince ASC, address.City ASC, customer.CustomerName ASC, orderheader.SalesOrderID ASC
```

Ahora, cada vez que la query se ejectura, será necesario dar un valor al parámetro ODI \(por ejemplo, 63222\). Ejecute la query al menos una vez antes de guardar el archivo.

## Create order-odiparam.ozr

Copie **`order-detail.ozr`** a **`order-odiparam.ozr`**.

**1. Usando el parámetro en el reporte**

1. Datainfo &gt; DataTree &gt; order &gt; OZParam &gt; Seleccione order ID
2. Properties &gt; Data &gt; configure el Field Value como "63222".
3. Preview

#### 2. Configurando y añadiendo el ParameterToolbar.

1. Components &gt; click-derecho en ParameterToolbar &gt; Refresh Toolbar Wizard
2.  Mueva order.orderID del panel izquierdo Selectable Parameter al panel derecho Selected Parameter.
3. Establezca las opciones como en la siguiente imagen.

![](../.gitbook/assets/image%20%286%29.png)

Previsualice \(preview\) el reporte. Ahora es posible modificar el valor del parámetro **order ID** \(ex: "69550"\) y refrescar el reporte con nueva informacion en tiempo real de forma dinámica.

![](../.gitbook/assets/image%20%281%29.png)

