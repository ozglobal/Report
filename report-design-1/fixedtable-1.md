# FixedTable

## Reporte Modelo

[Example](http://oz.ozeform.io/oz/edu/reportdev/order-detail.html)

## order-detail.ozr

Cree un nuevo ReportTemplate y guardelo como **`order-detail.ozr`**.

#### Añadiendo la banda Master

1. Añada una banda y dele el nombre de **master**.
2. Añada una FixedTable \(4x7\)
3. Data row height = 0.7cm, line spacing = 0.2cm
4. Filas con el Address y el Due date: utilice las opciones **Cell Merge** y **Cell Divide**
5. Escriba el nombre de los distintos campos
6. Asigne \(arrastrando y soltando desde la ventada de datos a la tabla\) los datos del dataset **order**

![](../.gitbook/assets/image%20%284%29.png)

#### Añadiendo la banda Detail

1. Añada una banda debajo de la banda Master y dele el nombre de **detail**.
2. Añada un Tabla \(Table\) con los campos ProductNumber, ProductName, OrderCity, UnitPrice, y Amount  del dataset **detail**. \(Refer to **`order-table.ozr`**\)

![](../.gitbook/assets/image%20%289%29.png)

#### Relación Master-Detail

1. Cambie el nombre de la banda superior a "**master**".
2. Cambie el nombre de la banda inferior a "**detail**".
3. Asegúrese de que la propiedad **Mater Name** de la banda **detail** tiene el valor de **master**.

#### Opciones

1. Seleccione la banda **detail**.
2. Establezca el valor de la propiedad **Fix Master** a **True**.
3. Establezca el valor de la propiedad  **Fix Title** a **True**.
4. Establezca la propiedad **Force New Page** a **True**.

