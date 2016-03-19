##Configuración de base de datos MySQL en Heroku
###Plugin Heroku/ClearDB

Para crear una base de datos MySQL asociada a su aplicación en Heroku, siga los siguientes pasos.

1. Autentíquese en Heroku, abra el Dashboard y seleccione la aplicación para la cual creará la base de datos.
2. Seleccione la opción de 'Recursos'. Si su aplicación ya tiene una base de datos Postgres asociada, elimínela:

	![](RemovePostgres.png)

3. En la caja de búsqueda de 'Add-ons' busque el plugin ClearDB, e instálelo (cuando se le pida, seleccione el botón de 'Provision':

	![](ClearDBSearch.png)
	![](Ignite.png)      

4. Una vez se haya creado la base de datos, puede indentificar los datos de conexión ingresando a 'Settings' y haciendo clic en 'Reveal Config Vars'. Copie el valor de la variable CLEARDB_DATABASE_URL:

	![](ShowConfigVars.png)

	La URL indicada tiene la siguiente estructura:

	```
	mysql://USER:PASSWORD@HOST/DATABASENAME?reconnect=true
```

	Es decir, que para la siguiente URL: 

	```
	mysql://b2adds22s553bd3:50232cc6@us-cdbr-iron-east-03.cleardb.net/heroku_87acf5efed82e1?reconnect=true
```
	Los siguientes serían los parámetros para conectarse con un cliente MySQL (por ejemplo, MySQLWorkbench):

	| Parámetro     | Valor         | 
| ------------- |:-------------|
| Host      | us-cdbr-iron-east-03.cleardb.net |
| Usuario     | b2adds22s553bd3      |
| Contraseña | 50232cc6      |
| Nombre de la base de datos | heroku_87acf5efed82e1      |

5. Para una aplicación Java, la URL de conexión quedaría como

	```
jdbc:mysql://b2adds22s553bd3:50232cc6@us-cdbr-iron-east-03.cleardb.net/heroku_87acf5efed82e1?reconnect=true   
```  
