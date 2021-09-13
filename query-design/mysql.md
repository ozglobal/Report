# Database Connection

## Using Dialog

1. In the Data view, right-click **DATABASE** and click **Add Store**.
2. In the **Add Database Connection Information** dialog,
3. Fill out connection information as below and click **OK**.

* **Name:** order \(ODI name\)
* **Vendor**: mysql
* **Database IP Address**: ozdemodb.cggbfyxtkcxr.sa-east-1.rds.amazonaws.com
* **Database Port number:** 3306
* **Database name:** ozdemodb
* **User name**: designer
* **Password**: password

## Using DB Connection Pool

#### db.properties

1. Go to the default working folder \(_**`C:\Users\username\Documents\OZRepository\)`**_ and create **`db.properties`**.
2. Add DB connection information below.

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

#### Connecting to database

1. In the **Add Database Connection Information** dialog,
2. Tick the checkbox **Alias** at the bottom and type in "demo"
3. Select the **db.properties** from the file browser.
4. Click **OK**.

## Database Information

1. Once connected to the database, tables are listed in the lower part of the Data view.
2. By right-clicking a table name you can see table field information or data rows \(max 100 rows by default\).
3. To change the max row count, go to **File** tab menu, select **Options &gt; Environment &gt; General**.

