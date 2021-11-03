---
description: Design datasets with Query Designer to use in the Report Designer
---

# Dataset Design

## OZ Data structure

### Data Store

A datastore is a data repository that supports various data sources. It supports functions such as connecting to a database, defining data, and configuring data fields. The data store types are listed below.

| Type        | Description                                                                                                                                                |
| ----------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| DATABASE    | A data source interface to JDBC/ODBC/OLEDB RDBMS, Dataset is defined by SQL.                                                                               |
| USER DATA   | A data source interface to external data sources like File data(Text, CSV, XML) or data from user applications (EJB, Servlet, ASP, JSP, Stored Procedure). |
| GROUP DATA  | Split a dataset of any data source into multiple datasets by the specified field. GDS is used to reconstruct a dataset into master-detail datasets.        |
| FILE STORE  | A data source interface to CSV file or XML file without DTD located on the server (accessed by path)                                                       |
| HTTP STORE  | A data interface to CSV file or XML file without DTD located on the web (accessed by URL)                                                                  |
| SOAP STORE  | A data source interface to the data from web services.                                                                                                     |
| XML         | A data source interface to an XML file with DTD/XSD                                                                                                        |
| SAP         | A data source interface to data from SAP R/3 RFC.                                                                                                          |
| CLEAR QUEST | A data source interface to the database from IBM Rational Clear Quest program                                                                              |
| Transaction | Support DML transaction                                                                                                                                    |

### Dataset

Dataset is a set of data fields selected from a data store. The way to define a dataset depends on the types of data store. Dataset for database store is defined by a query.

### ODI (OZ Data Information)

ODI is a file in XML format storing data stores. OZ Report Designer uses ODI to map or bind report forms to data.

### Hierarchy of ODI

A single ODI file can have multiple data stores and one data store can have multiple datasets.

## Creating ODI

### Query design mode

| Mode         | Description                                      |
| ------------ | ------------------------------------------------ |
| Design View  | Easy way with drag & drop                        |
| Manual       | Write down or copy query into the query editor   |
| Query Wizard | Generate an advanced query in an interactive way |

### Query Wizard

| Tab      | Description                           |
| -------- | ------------------------------------- |
| TABLE    | Select tables for FROM clause         |
| FIELD    | Select columns for a select list      |
| JOIN     | Define Join conditions                |
| WHERE    | Define WHERE conditions               |
| GROUP BY | Define GROUP BY and HAVING conditions |
| ORDER BY | Define ORDER BY conditions            |

## Create order.odi

### 1. Add \<order> dataset

**Using Query Wizard**

![](<../.gitbook/assets/image (5).png>)

#### Using Manual mode

1. Menu bar > Query > Design Mode > Manual
2. Copy the query below to the Query editor

```sql
-- order
SELECT orderheader.SalesOrderID, customer.Channel, customer.CustomerName, orderheader.DueDate, orderheader.ShipDate, orderheader.TotalDue, customer.EmailAddress, customer.Phone, address.PostalCode, address.Country, address.StateProvince, address.City, address.AddressLine1, orderheader.PurchaseOrderNumber 
FROM orderheader 
INNER JOIN customer ON customer.CustomerID = orderheader.CustomerID
INNER JOIN address ON address.AddressID = orderheader.AddressID
ORDER BY address.Country ASC, address.StateProvince ASC, address.City ASC, customer.CustomerName ASC, orderheader.SalesOrderID ASC
```

### 2. Add \<detail> dataset

```sql
SELECT orderdetail.SalesOrderID, product.ProductNumber, product.ProductName, orderdetail.OrderQty, orderdetail.UnitPrice, orderdetail.OrderQty * orderdetail.UnitPrice AS Amount 
FROM orderdetail 
INNER JOIN product ON product.ProductID = orderdetail.ProductID
WHERE orderdetail.SalesOrderID = #order.SalesOrderID#
```

### 3. Create Master-Detail relationship

1. Select the **detail **dataset.
2. Set the **Master Set** property to **order**.
