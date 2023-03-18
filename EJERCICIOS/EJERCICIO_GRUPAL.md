https://www.db-fiddle.com/f/s77gC6K91difutRLEhXG3x/0




https://www.db-fiddle.com/f/rU1JaeiYSMfanaXbZwUE5b/0

USE tienda;

/* obtienes la media d elos valores*/

SELECT avg (precio) AS 'Promedio de los precios'
FROM producto;

/*Cuenta el numero de productos*/

SELECT count (nom_prod) AS 'Cantidad de productos'
FROM producto;

/* busca el precio maximo*/

SELECT max (precio) AS 'Precio mas alto'
FROM producto;

/* Busca el precio mas barato*/

SELECT MIN (precio) AS 'Precio mas bajo'
FROM producto;


/*Cuenta los numeros de caracteres de los datos*/

SELECT CHAR_LENGTH (nom_clie)
FROM cliente;


/*MUESTRA LA FECHA DEL SISTEMA*/

SELECT NOW();


/*Convertir de mayus a minus, se utiliza para dar homogeneidad a los datos*/

SELECT UCASE (nom_clie) AS 'Nombres clientes'
FROM cliente;


/*Convertir de minus a mayus, se utiliza para dar homogeneidad a los datos*/

SELECT LCASE (nom_clie) AS 'Nombres de clientes'
FROM cliente;


/*FORMAT DA UN FORMATO ESPECIFICO A COMO SE MUETSRAN LOS PRECIOS*/


SELECT FORMAT (precio, 2)
FROM producto;


/*Mostrar tabla de ventas*/

SELECT * 
From nota;

/*Mostrando le nombre del cliente y que producto compro, RIGHT Muestra los clientes aunque no hayan comprado */

SELECT nom_prod, nom_clie
FROM producto RIGHT JOIN nota ON nota.clave_prod1=producto.clave_prod
RIGHT JOIN cliente ON cliente.clave_clie=nota.clave_clie1;

![image](https://user-images.githubusercontent.com/113804528/226143364-38db15a8-e820-4b4a-a31d-66d81192e560.png)




/*Mostrando le nombre del cliente y que producto compro, LEFT Muestra los productos aunque no hayan sido comprados*/

SELECT nom_prod, nom_clie
FROM producto LEFT JOIN nota ON nota.clave_prod1=producto.clave_prod
LEFT JOIN cliente ON cliente.clave_clie=nota.clave_clie1;
![image](https://user-images.githubusercontent.com/113804528/226143407-17378268-64ab-4be9-ba4e-245a6a769e0e.png)



/*Mostrando le nombre del cliente y que producto compro, INNER, Muestra los clientes y productos con interacción, quien compro y que compro*/

SELECT nom_prod, nom_clie
FROM producto INNER JOIN nota ON nota.clave_prod1=producto.clave_prod
INNER JOIN cliente ON cliente.clave_clie=nota.clave_clie1;

![image](https://user-images.githubusercontent.com/113804528/226143442-bc6ef582-9d2b-4159-b481-12366a86f5ec.png)



