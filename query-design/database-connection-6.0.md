# Database Connection (6.0)

## Using Dialog

1. In the Data view, right-click **DATABASE** and click **Add Store**.
2. In the** Add Database Connection Information** dialog,
3. Fill out connection information as below and click **OK**.

* **Name: **order (ODI name)
* **Vendor**: user
* **Driver Class Name**: com.mysql.jdbc.Driver
* **Connection URL**: jdbc:mysql://127.0.0.1:3306/ozdemodb
* **User name**: username
* **Password**: password

## Using DB Connection Pool

#### db.properties

1. Go to the default working folder (_**`C:\Users\username\Documents\OZRepository\)`**_ and create **`db.properties`**.
2. Add DB connection information below.

{% code title="db.properties" %}
```
demo.vendor=USER
demo.driver=com.mysql.jdbc.Driver
demo.url=jdbc:mysql://127.0.0.1:3306/ozdemodb
demo.user=user
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

#### Connecting to database

1. In the **Add Database Connection Information** dialog,
2. Tick the checkbox **Alias **at the bottom and type in "demo"
3. Select the **db.properties** from the file browser.
4. Click **OK**.

## Database Information

1. Once connected to the database, tables are listed in the lower part of the Data view.
2. By right-clicking a table name you can see table field information or data rows (max 100 rows by default).
3. To change the max row count, go to **File** tab menu, select **Options > Environment > General**.
