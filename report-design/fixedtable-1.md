# FixedTable

## Target Report

[Example](http://oz.ozeform.io/oz/edu/reportdev/order-detail.html)

## order-detail.ozr

Create a new ReportTemplate and save it as **`order-detail.ozr`**.

#### Add Data band for master

1. Add a Data band named **master**.
2. Add a FixedTable (4 by 7)
3. Data row height = 0.7cm, line spacing = 0.2cm
4. Lines for Address and Due date: use **Cell Merge** and **Cell Divide**
5. Put field titles.
6. Assign dataset field values from the dataset **order**.

![](<../.gitbook/assets/image (4).png>)

#### Add Data band for detail

1. Add a Data band named **detail** below the **master **band.
2. Add a Table component with ProductNumber, ProductName, OrderCity, UnitPrice, Amount from the **detail **dataset. (Refer to **`order-table.ozr`**)

![](<../.gitbook/assets/image (9).png>)

#### Master-Detail relationship

1. Change the Name of the upper Data band to "**master**".
2. Change the Name of the lower Data band to "**detail**".
3. Make sure the **Mater Name** property of the **detail **band is **master**.

#### Options

1. Select the **detail **band.
2. Set the **Fix Master **property to **True**.
3. Set the **Fix Title **property to **True**.
4. Set the **Force New Page** property to **True**.
