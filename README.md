Antes de docker compose up se deben crear los secret y el .env

crear la carpeta secrets y dentro poner 4 archivos con sus respectivos valores
  db_user_name.txt
  db_user_password.txt
  db_root_password.txt
  db_name.txt

agretar tambien en el archivo .env 

DB_USERNAME=
DB_PASSWORD=
DB_NAME=
DB_HOST=

con sus respectivos valores 

DB_HOST siendo el nombre del servicio db dentro del dockerfile