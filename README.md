# Select, Insert, Update, y Delete - MySQL
En este repositorio realizaré pruebas haciendo uso de las funciones Select, Insert, Update y Delete en una base de datos proporcionada por MySQL utilizando la herramiento MySQL Workbench.

## Importando la base de datos


<p align="center">
	<img src="https://raw.githubusercontent.com/WilliamLopez663/Select-Insert-Update-y-Delete---MySQL/main/assets/images/importar-basededatos1.PNG">
</p>
<p align="center">
	<img src="https://raw.githubusercontent.com/WilliamLopez663/Select-Insert-Update-y-Delete---MySQL/main/assets/images/importar-basededatos2.PNG">
</p>
<br>

- Tras importar la base de datos se visualizan las tablas cargadas:
<p align="center">
	<img src="https://raw.githubusercontent.com/WilliamLopez663/Select-Insert-Update-y-Delete---MySQL/main/assets/images/importar-basededatos3.PNG">
</p>
<br>

- Para verificar el que el import se realizó de manera correcto MySQL recomienda realizar la siguiente prueba:
<p align="center">
	<img src="https://raw.githubusercontent.com/WilliamLopez663/Select-Insert-Update-y-Delete---MySQL/main/assets/images/prueba1-import.PNG">
</p>
<br>

- Se puede visualizar que la pureba se está realizando de manera correcta:

<p align="center">
	<img src="https://raw.githubusercontent.com/WilliamLopez663/Select-Insert-Update-y-Delete---MySQL/main/assets/images/prueba2-import.PNG">
</p>
<br><br>

## Select
- Traer todos los datos de una tabla:  
  `SELECT * FROM city;`  
<p align="center">
	<img src="https://raw.githubusercontent.com/WilliamLopez663/Select-Insert-Update-y-Delete---MySQL/main/assets/images/select-toda-la-tabla.PNG">
</p>
<br>

- Traer una columna específica:  
  `SELECT name FROM city;`  
<p align="center">
	<img src="https://raw.githubusercontent.com/WilliamLopez663/Select-Insert-Update-y-Delete---MySQL/main/assets/images/select-columna-especifica.PNG">
</p>
<br>

- Traer una columna específica pero indicandole un alias:  
  `SELECT name AS Nombre FROM city;`  
<p align="center">
	<img src="https://raw.githubusercontent.com/WilliamLopez663/Select-Insert-Update-y-Delete---MySQL/main/assets/images/select-columna-especifica-alias.PNG">
</p>
<br>

- Traer varias columnas e indicandole un alias a cada columna:  
  `SELECT name AS Nombre, district AS Distrito, population AS Población FROM city;`  
<p align="center">
	<img src="https://raw.githubusercontent.com/WilliamLopez663/Select-Insert-Update-y-Delete---MySQL/main/assets/images/select-columnas-alias.PNG">
</p>
<br>

- Uso de la clausula `WHERE` para traer información filtrada:  
  `SELECT name AS Nombre, CountryCode AS Código, population AS Población FROM city WHERE CountryCode = "ARG";`  
<p align="center">
	<img src="https://raw.githubusercontent.com/WilliamLopez663/Select-Insert-Update-y-Delete---MySQL/main/assets/images/clausula-where.PNG">
</p>
<br>

- Filtros compuestos usando `WHERE` y `AND`:  
  `SELECT name AS Nombre, CountryCode AS Código, population AS Población FROM city WHERE CountryCode = "ARG" AND population > 400000;`  
<p align="center">
	<img src="https://raw.githubusercontent.com/WilliamLopez663/Select-Insert-Update-y-Delete---MySQL/main/assets/images/select-where-and.PNG">
</p>
<br>

- Filtros compuestos usando `WHERE` y `OR`:  
  `SELECT name AS Nombre, CountryCode AS Código, population AS Población FROM city WHERE CountryCode = "ECU" OR CountryCode = "AFG";`  
<p align="center">
	<img src="https://raw.githubusercontent.com/WilliamLopez663/Select-Insert-Update-y-Delete---MySQL/main/assets/images/select-where-or.PNG">
</p>
<br>

- Filtros compuestos usando `WHERE` y `NOT`:  
  `SELECT Name, Population FROM country WHERE NOT Population < 100000000;`  
<p align="center">
	<img src="https://raw.githubusercontent.com/WilliamLopez663/Select-Insert-Update-y-Delete---MySQL/main/assets/images/select-where-not.PNG">
</p>
<br>

- Ordenando usando `ORDER BY`:  
  `SELECT Name, Population FROM country ORDER BY population DESC;`  
<p align="center">
	<img src="https://raw.githubusercontent.com/WilliamLopez663/Select-Insert-Update-y-Delete---MySQL/main/assets/images/select-orderby.PNG">
</p>
<br>


- Quitando duplicados usando  `DISTINCT`:  
  `SELECT DISTINCT countrycode FROM city;`  
<p align="center">
	<img src="https://raw.githubusercontent.com/WilliamLopez663/Select-Insert-Update-y-Delete---MySQL/main/assets/images/select-distinct.PNG">
</p>
<br>

- Buscando similares o que contengan ciertos caracteres con `LIKE`:  
  `SELECT * FROM country WHERE name LIKE '%stan';`  
<p align="center">
	<img src="https://raw.githubusercontent.com/WilliamLopez663/Select-Insert-Update-y-Delete---MySQL/main/assets/images/select-like.PNG">
</p>
<br>

- Filtrando por conjunto `IN`:   
  `SELECT * FROM country where continent in ('north america', 'south america');`  
<p align="center">
	<img src="https://raw.githubusercontent.com/WilliamLopez663/Select-Insert-Update-y-Delete---MySQL/main/assets/images/select-in.PNG">
</p>
<br>

- Filtrando rangos `BETWEEN`:   
  `SELECT * FROM country where population between 15000000 and 20000000;`  
<p align="center">
	<img src="https://raw.githubusercontent.com/WilliamLopez663/Select-Insert-Update-y-Delete---MySQL/main/assets/images/select-between.PNG">
</p>
<br>

- Seleccionando nulos `IS NULL`:   
  `SELECT * FROM country where capital is null;`  
<p align="center">
	<img src="https://raw.githubusercontent.com/WilliamLopez663/Select-Insert-Update-y-Delete---MySQL/main/assets/images/select-is-null.PNG">
</p>
<br>

- Seleccionando con funciones agregadas `COUNT, AVG, MAX`:   
  `SELECT max(population) FROM country;;`  
<p align="center">
	<img src="https://raw.githubusercontent.com/WilliamLopez663/Select-Insert-Update-y-Delete---MySQL/main/assets/images/select-max.PNG">
</p>
<br>

- Agrupando con `GROUP BY`:   
  `SELECT SUM(Population) FROM country group by CONTINENT;`  
<p align="center">
	<img src="https://raw.githubusercontent.com/WilliamLopez663/Select-Insert-Update-y-Delete---MySQL/main/assets/images/select-groupby.PNG">
</p>
<br>

- Filtrando funciones agregadas con `HAVING`:   
  `SELECT continent, count(*) as Paises FROM country group by CONTINENT HAVING COUNT(*) > 5;`  
<p align="center">
	<img src="https://raw.githubusercontent.com/WilliamLopez663/Select-Insert-Update-y-Delete---MySQL/main/assets/images/select-having.PNG">
</p>
<br>

- Subconsultas:   
  `SELECT name as Nombre, population as poblacion FROM country where population > ( select avg(population) from country);`  
<p align="center">
	<img src="https://raw.githubusercontent.com/WilliamLopez663/Select-Insert-Update-y-Delete---MySQL/main/assets/images/subconsultas-select.PNG">
</p>
<br>

- Uniendo consulatas con `INNER JOIN`:   
  `select * from city ci inner join country co on ci.name = co.name;`  
<p align="center">
	<img src="https://raw.githubusercontent.com/WilliamLopez663/Select-Insert-Update-y-Delete---MySQL/main/assets/images/select-inner-join.PNG">
</p>
<br>

- Consulatas utilizando `CASE`:   
`select name as Pais, population as Población, case`  
`when population > 100000000 then 'Población Alta'`  
`when population between 10000000 and 100000000 then 'Población Media'`  
`when population < 10000000 then 'Población baja'`  
`end as Nivel_de_Poblacion from country;`  
<p align="center">
	<img src="https://raw.githubusercontent.com/WilliamLopez663/Select-Insert-Update-y-Delete---MySQL/main/assets/images/select-case.PNG">
</p>
<br>

- Limitando la cantidad de filas con `LIMIT`:   
  `select name as País, population as Población from country order by population desc limit 10;`  
<p align="center">
	<img src="https://raw.githubusercontent.com/WilliamLopez663/Select-Insert-Update-y-Delete---MySQL/main/assets/images/select-limit.PNG">
</p>
<br>

- Uniendo columnas de diferentes tablas con `UNION`:   
  `SELECT name AS País FROM country UNION SELECT countrycode AS code FROM city;`  
<p align="center">
	<img src="https://raw.githubusercontent.com/WilliamLopez663/Select-Insert-Update-y-Delete---MySQL/main/assets/images/select-union.PNG">
</p>
<br>

- Pasando a mayúsculas con `UPPER`:   
  `SELECT upper(name) AS País FROM country;`  
<p align="center">
	<img src="https://raw.githubusercontent.com/WilliamLopez663/Select-Insert-Update-y-Delete---MySQL/main/assets/images/select-upper.PNG">
</p>
<br>

