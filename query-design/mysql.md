# Conexión a la Base de Datos \(DB\)

## Mediante el Cuadro de Diálogo

1. En la ventana de Data view, haga click-derecho en **DATABASE** y seleccione **Add Store**.
2. En el cuadro de diálogo **Add Database Connection Information**,
3. Rellene los parametros con la siguiente información y pulse **OK**.

* **Name:** order \(ODI name\)
* **Vendor**: mysql
* **Database IP Address**: ozdemodb.cggbfyxtkcxr.sa-east-1.rds.amazonaws.com
* **Database Port number:** 3306
* **Database name:** ozdemodb
* **User name**: designer
* **Password**: password

## Mediante Connection Pool \(agrupamiento de conexiones\)

#### db.properties

1.      \(_**`C:\Users\username\Documents\OZRepository\)`**_ y cree un archivo de texto **`db.properties`**.
        \(_**`C:\Users\username\Documents\OZRepository\)`**_ y cree un archivo de texto **`db.properties`**.

2. Añada la siguiente información.

{% code title="db.properties" %}
```text
# for MySQL, MariaDB
# 'demo' will be the Alias name
demo.vendor=mysql
#demo.serverAddress=127.0.0.1
demo.serverAddress=ozdemodb.cggbfyxtkcxr.sa-east-1.rds.amazonaws.com
demo.portNo=3306
demo.dbName=ozdemodb
demo.user=designer
demo.password=password
demo.maxconns=20
demo.initconns=5
demo.timeout=5
demo.initSqls=
demo.closeSqls=
demo.doConnectionCheck=true
demo.testQueryString=select 1
demo.sessionQuery=
demo.encodecharset=
demo.decodecharset=
demo.fetchrow=0
demo.ignoreQueryError=false
```
{% endcode %}

#### Conectándose a la base de datos

1. En el cuadro de diálogo **Add Database Connection Information**,
2. Marque la casilla **Alias** situada en la parte inferior y escriba "demo".
3. Busque y seleccione el archivo **db.properties** editado en el paso anterior.
4. Pulse **OK**.

## Información Sobre la Base de Datos

1. Tras conectarse a la base de datos con éxito, una lista de las tablas contenidas en ella se mostrará en la zona inferior de la ventana Data view.
2. Haciendo click-derecho en el nombre las tablas, se puede previsualizar informacion sobre las columnas de la tabla o sobre los datos contenidos en ésta \(con la configuración inicial, se muestran 100 filas\).
3. Para modificar el número de filas mostradas, vaya al menu general **File**, seleccione **Options &gt; Environment &gt; General**.

