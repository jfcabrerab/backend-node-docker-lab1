Antes de docker compose up se deben crear los secret y el .env

crear la carpeta secrets y dentro poner 4 archivos con sus respectivos valores

 > db_user_name.txt
 > db_user_password.txt
 > db_root_password.txt
 > db_name.txt

agretar tambien en el archivo .env 

> DB_USERNAME=
> DB_PASSWORD=
> DB_NAME=
> DB_HOST=

con sus respectivos valores 

*DB_HOST siendo el nombre del servicio db dentro del dockerfile*

recordar crear la tabla de usuarios

yo lo hice utilizando:

```
docker compose exec db sh -lc 'mysql -uroot -p"$(cat /run/secrets/db_root_password)" lab1 -e "CREATE TABLE usuarios (id INT NOT NULL AUTO_INCREMENT, nombre VARCHAR(255) NULL, edad INT NULL, created_at DATE NULL, updated_at DATE NULL, PRIMARY KEY (id));"'
```
y agregar un usuario:

```
curl -X POST http://localhost:4000/users -H "Content-Type: application/json" -d '{"nombre":"Carlos López","edad":28}'	
```