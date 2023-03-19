# printdalo
Impresion de voucher daloradius desde php buscando en batch o lote creado

- Pagina php ,extrae los usuarios desde la base de datos de daloradius y crea los vouchers, modificar en el `print/index.php` algunas configuraciones de la base de datos por ejemplo en la linea 35

```
 $con = mysqli_connect("localhost","radius","84Uniq@","radius");
```
El servidor es `localhost`, el usuario es `radius` ,la contraseña es `84Uniq@` y La base de datos se llama `radius`.

- En la linea 40
```
$query = "SELECT * FROM radius.fichas WHERE CONCAT(batch_name) LIKE '%$filtervalues%'";
```

se selecciona en donde estan los usuarios de la base de datos `fichas` y filtramos en la busqueda `batch_name`

- Se toman valores de la tabla `planname` el cual es el plan de los vauchers creados , `plancost` se refiere al costo de las fichas,`username` son los usuarios y `value` las contraseñas

la base de datos usada es la de mi tutorial >> `https://github.com/wirisp/Daloradius-Wireguard-Pihole-unbound`
```
mysql -p -u root radius < /root/dbname.sql
```
