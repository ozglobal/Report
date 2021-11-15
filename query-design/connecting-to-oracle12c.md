# Connecting to Oracle12C

#### Oracle jdbc driver

1. Get [ojdbc6.jar](https://drive.google.com/file/d/1tVKCshDjUjjrRNc0iOD7rCsNuKs0746W/view?usp=sharing)
2. Put it in C:\Program Files (x86)\Forcs\OZ Report 6.0\OZ Query Designer 6.0\UniversalDriver
3. Delete classes12.jar and classes12.zip from UniversalDriver.
4. Open ..\config\launch.cfg, find "classes.zip", and change it to "ojdbc6.jar".
5. Add database alias definition in the db.properties

{% code title="db.properties" %}
```
ora.vendor=oracle
ora.serverAddress=end-point
ora.portNo=1521
ora.sid=ORCL
ora.user=user
ora.password=password
ora.maxconns=20
ora.initconns=5
ora.timeout=5
ora.doConnectionCheck=false
ora.sessionQuery=
ora.doConnectionCheck=
ora.testQueryString=
ora.decodecharset=
ora.encodecharset=
ora.fetchrow=
ora.ignoreQueryError=false
```
{% endcode %}
