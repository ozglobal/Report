---
description: Design datasets with Query Designer to use in the Report Designer
---

# Diseño de Set de Datos

## Estructura de Datos OZ

### Data Store

Un data store es un repositorio con datos que pueden provenir de varios tipos diferentes de fuentes de datos. Incluye diversas funciones, como conectarse a una base de datos, definir datos, y configurar los distintos campos \(data fields\) . A continuación puede verse una lista con los distintos tipos de data store.

| Type | Description |
| :--- | :--- |
| DATABASE | Interfaz de fuentes de datos para JDBC/ODBC/OLEDB RDBMS. Los datasets se definen mediante SQL. |
| USER DATA | Interfaz de fuentes de datos para fuentes externas de tipo TXT, CSV, o XML, o para datos que provienen de aplicaciones de usuario \(EJB, Servlet, ASP, JSP, Stored Procedure\). |
| GROUP DATA | Divide un dataset proveniente de cualquier fuente en múltiples datasets a partir de una columna \(campo\) específica. GDS is usado para reconstruir el dataset en datasets con jerarquías Master-Detail. |
| FILE STORE | Interfaz de fuentes de datos para archivos CSV o XML sin DTD localizados en el servidor \(accedidos mediante una ruta\) |
| HTTP STORE | Interfaz de fuentes de datos para archivos CSV o XML sin DTD localizados en la web \(accedidos mediante un URL\) |
| SOAP STORE | Interfaz de fuentes de datos para servicios web |
| XML | Interfaz de fuentes de datos para archivos XML con DTD/XSD |
| SAP | Interfaz de fuentes de datos para datos provenientes de SAP R/3 RFC |
| CLEAR QUEST | Interfaz de fuentes de datos para la base de datos IBM Rational Clear Quest program |
| Transaction | Soporte para transacciones DML  |

### Set de Datos \(Dataset\)

Un Dataset es un set de datos extraido de un data store. La forma de definir un dataset depende del tipo de datastore al que se acceda. Los datasets creados a partir de una base de datos se definen mediante una query \(consulta\).

### ODI \(OZ Data Information\)

ODI es un archivo en formato XML que contiene data stores.  OZ Report Designer utiliza los archivos ODI para mapear y mostrar la informacion de las fuentes de datos en los reportes.

### Jerarquía de los archivos ODI

Un solo archivo ODI puede incluir multiples data stores y un solo data store puede contener multiples datasets.

## Creando el archivo ODI

### Query design mode

| Modo | Descripción |
| :--- | :--- |
| Design View | Interfaz sencilla para poder crear queries simples arrastrando y soltando las tablas y seleccionando los campos. |
| Manual | Escriba o copie y pegue una query en el editor de queries. |
| Query Wizard | Genere una query avanzada de forma interactiva. |

### Query Wizard

| Tab | Description |
| :--- | :--- |
| TABLE | Seecciona tablas para la cláusula FROM |
| FIELD | Selecciona campos \(columnas\) de la lista seleccionada |
| JOIN | Define la condición JOIN |
| WHERE | Define la condición WHERE |
| GROUP BY | Define las condiciones GROUP BY y HAVING |
| ORDER BY | Define la condición ORDER BY |

## Creando order.odi

### 1. Añadiendo el dataset &lt;order&gt;

**Mediante el Query Wizard \(asistente de consultas\)**

![](../.gitbook/assets/image%20%285%29.png)

#### Mediante el modo manual \(Manual Mode\)

1. Menu bar &gt; Query &gt; Design Mode &gt; Manual
2. Copie y pegue la siguiente query en el editor de queries.

```sql
-- order
SELECT orderheader.SalesOrderID, customer.Channel, customer.CustomerName, orderheader.DueDate, orderheader.ShipDate, orderheader.TotalDue, customer.EmailAddress, customer.Phone, address.PostalCode, address.Country, address.StateProvince, address.City, address.AddressLine1, orderheader.PurchaseOrderNumber 
FROM orderheader 
INNER JOIN customer ON customer.CustomerID = orderheader.CustomerID
INNER JOIN address ON address.AddressID = orderheader.AddressID
ORDER BY address.Country ASC, address.StateProvince ASC, address.City ASC, customer.CustomerName ASC, orderheader.SalesOrderID ASC
```

### 2. Añadiendo el dataset &lt;detail&gt;

```sql
SELECT orderdetail.SalesOrderID, product.ProductNumber, product.ProductName, orderdetail.OrderQty, orderdetail.UnitPrice, orderdetail.OrderQty * orderdetail.UnitPrice AS Amount 
FROM orderdetail 
INNER JOIN product ON product.ProductID = orderdetail.ProductID
WHERE orderdetail.SalesOrderID = #order.SalesOrderID#
```

### 3. Creando una relación Master-Detail

1.  Seleccione el  dataset **detail**.
2.  Establezca el valor de la propiedad **Master Set** como **order**.

