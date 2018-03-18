# practicaSQL
<h1>Ejercicios para prácticar SQL</h1>
	<h3>LENGUAJE DDL</h3>
<p>1.Crea una base de datos denominada vuelos. Con las siguientes características:</p>
<ul>
<li>Character set = Latin1</li>
<li>Collate = latin1_spanish_ci</li>
</ul>
<p><strong>CREATE DATABASE vuelos CHARACTER SET Latin1 COLLATE Latin1_spanish_ci</strong></p>
<p>2.Renombra la base de datos a viajes.</p>

<p><strong>CREATE DATABASE viajes CHARACTER SET Latin1 COLLATE Latin1_spanish_ci</strong></p>
<p><strong>DROP DATABASE vuelos;</strong></p>
<p>3.Crea una tabla denominada clientes que contendrá los siguientes campos:</p>
<ul>
	<li>id</li>
		<ul>		
			<li>Integer</li>
			<li>autoincremental</li>
			<li>not_null</li>
			<li>primary_key</li>
		</ul>
	<li>nombre</li>
		<ul>
			<li>varchar(50)</li>
		</ul>
	<li>apellidos</li>
		<ul>
			<li>varchar(50)</li>
		</ul>
	<li>direccion</li>
		<ul>
		<li>varchar(150)</li>
		</ul>
</ul>

	<p><strong>CREATE TABLE clientes(</strong></p>
	<p><strong>id integer unsigned ZEROFILL AUTO_INCREMENT,</strong></p>
    	<p><strong>nombre varchar(50),</strong></p>
	<p><strong>apellidos varchar(50),</strong></p>
	<p><strong>direccion varchar(150),</strong></p>
    	<p><strong>PRIMARY KEY(id)</strong></p>
	<p><strong>);</strong></p>

<p>4.Crea una tabla denominada viajes que contendrá los siguientes campos:</p>
<ul>
	<li>id</li>
	<ul>
		<li>Integer</li>
		<li>autoincremental</li>
		<li>not_null</li>
		<li>primary_key</li>
	</ul>
	<li>titulo</li>
	<ul>
		<li>varchar(50)</li>
	</ul>
	<li>descripcion</li>
	<ul>
		<li>varchar(150)</li>
	</ul>
	<li>codigoCliente *Integer *Forgein key clientes(id)</li>
</ul>

	<p><strong>CREATE TABLE viajes(</strong></p>
	<p><strong>id integer unsigned ZEROFILL AUTO_INCREMENT,</strong></p>
    	<p><strong>titulo varchar(50),</strong></p>
	<p><strong>descripcion varchar(150),</strong></p>
    	<p><strong>codigoCliente integer unsigned ZEROFILL,</strong></p>
    	<p><strong>PRIMARY KEY(id),</strong></p>
    	<p><strong>INDEX (codigoCliente),</strong></p>
    	<p><strong>FOREIGN KEY (codigoCliente) REFERENCES clientes(id) on UPDATE CASCADE on DELETE RESTRICT</strong></p>
	<p><strong>);</strong></p>

<h3>LENGUAJE DML</h3>
<p>1. Utilizando la base de datos Sakila (BD de Pruebas de MySQL) Extraer todos los actores de la tabla actors.</p>

		<p><strong>SELECT * from actor</strong></p>
	
<p>2. De la tabla actors queremos conocer todos los nombres existentes en la tabla sin que se repita para ello utilizaremos DISTINCT.</p>

		<p><strong>SELECT DISTINCT(first_name) from actor</strong></p>

<p>3. De la tabla film queremos obtener una relación de películas que cumplan las siguientes características:</p>
<ul>
<li>rental_duration = 6</li>
<li>rental_rate >=2.99</li>
</ul>
<p><strong>SELECT * FROM film WHERE rental_duration=6 and rental_rate>=2.99</strong></p>
<p>4. De la tabla film queremos obtener una relación de la películas que tengan un replacement_cost entre 15.99 y 22.99</p>

<p><strong>SELECT * FROM film WHERE replacement_cost BETWEEN 15.99 AND 22.99</strong></p>
	

<p>5. Queremos Obtener todos los customers mediante el filtro de pertenencia a conjuntos IN que cumpla los siguientes requisitos.</p>
<ul>
	<li>Pertenecen al store 1</li>
	<li>Y su first_name = MARY, o NANCY o DONNA.</li>
</ul>	
<p><strong>SELECT * FROM customer WHERE store_id=1 and first_name in('MARY','NANCY','DONNA')</strong></p>


