# Master-Detail

## Target Report

[Example](http://oz.ozeform.io/oz/edu/reportdev/order-detail.html)

## order-detail.ozr

Create a new ReportTemplate and save it as **`order-detail.ozr`**.

#### Add Data band for master

1. Add a Data band named **order**.
2. Add a FixedTable (4 by 7)
3. Data row height = 0.7cm, line spacing = 0.2cm
4. Lines for Address and Due date: use **Cell Merge** and **Cell Divide**
5. Put field titles.
6. Assign dataset field values from the dataset **order**.

![](<../.gitbook/assets/image (4).png>)

#### Add Data band for detail

1. Add a Data band named **detail** below the **order **band.
2. Add a FixedTable component with 6 by 1.
3. Assign fields from the **detail **dataset to the 6 cells.

![](<../.gitbook/assets/image (10).png>)

Master Band settings

1. Right-click the detail data band to open Master Band Settings dialog.
2. Select \<order> as Master band.
3. Select a SalesOrderID and click the Connected button (or connect by dragging).

![](<../.gitbook/assets/image (12).png>)

#### Options

1. Select the **detail **band.
2. Set the **Fix Master **property to **True**.
3. Set the **Fix Title **property to **True**.
4. Set the **Force New Page** property to **True**.
