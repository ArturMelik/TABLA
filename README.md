CREATE DATABASE empresa_reparto;
use empresa_reparto;
CREATE TABLE tipoempresa(
    id_tipoempresa int PRIMARY key AUTO_INCREMENT,
    tipoempresa varchar(30));
    	INSERT INTO tipoempresa VALUES 
(1, "Autonomo"), 
(2,"Sociedad Limitada"), 
(3,"Sociedad Anonima");
CREATE TABLE provincia(
	id_provincia int PRIMARY KEY AUTO_INCREMENT,
    provincia varchar(20));
    	INSERT INTO provincia VALUES 
(1, "Madrid"), 
(2,"Valencia"), 
(3,"Barcelona"), 
(4,"Bilbao");
                                                                                     
CREATE table localidad(
	id_localidad int PRIMARY KEY AUTO_INCREMENT,
    localidad varchar(30),
	IDPROVINCIA INT);
	INSERT INTO localidad VALUES 
(1, "San Sebastian de los Reyes",1), 
(2, "Madrid",1), 
(3, "Cheste",2), 
(4, "Valencia",2), 
(5, "Hospitalet",3), 
(6, "Barcelona",3), 
(7, "Bilbao",4);
		
CREATE table clientes (
    id_cliente INT PRIMARY KEY AUTO_INCREMENT,
    nif varchar (10),
    nombre varchar(50),
    direccion varchar(50),
    id_localidad int,
    id_provincia int,
    id_tipoempresa int );

	INSERT INTO clientes VALUES 
(1, "25143625T", "Pepe Gotera", "C/ Pedro 23",1,1,1), 
(2, "56897458T", "Andrea Sanchez", "C/ Remedios 6",5,3,1), 
(3, "B65896958", "Lito S.L.", "C/Esperanza 5",2,1,2), 
(4, "A58475848", "MOD S.A", "C/Electricistas 56", 3,2,3), 
(5, "B96251425", "MFD S.L.", "C/Obrador 5", 4,2,2), 
(6, "54785698Y", "Jose Andres", "C/Prueba 25",6,3,1);

CREATE TABLE telefono_clientes(
	id_telefonoclientes int primary key auto_increment,
	id_cliente int,
	id_numerotelefono int);
		INSERT INTO telefono_clientes(id_cliente, id_numerotelefono) VALUES 
	(1, 915478569),
	(1,658963258),
	(1,785632589),
	(3,569874563),
	(4,632236566),
	(5,654632651),
	(6,689745896);
CREATE TABLE comerciales (
	id_comercial int primary key auto_increment,
	nombre_comercial varchar(20));
	INSERT INTO comerciales VALUES
(1,"Marta"),
(2,"Juan"),
(3,"Joaquin");

CREATE TABLE tipo_entregas (
id_tipoentregas int primary key auto_increment,
tipo_entregas varchar(20));
	INSERT INTO tipo_entregas VALUES 
(1,"EXPRESS"),
(2,"URGENTE"),
(3,"NORMAL");

CREATE TABLE pedidos (
id_pedidos int primary key auto_increment,
id_cliente int,
id_tipoentregas int,
peso double (5,2),
id_comercial int,
fecha date,
id_localidadentrega int);
	INSERT INTO pedidos (id_cliente, id_tipoentregas, peso, id_comercial, fecha, id_localidadentrega) VALUES 
(1, 1, 15, 1, "2019/02/12", 2),
(2, 2, 0.5, 2, "2019/03/12", 6),
(3, 3, 100, 3, "2019/04/12", 2),
(4, 1, 0.62, 2, "2019/09/12", 4),
(3, 1, 1, 1, "2019/05/12", 2),
(5, 3, 0.52, 2, "2019/06/12", 4),
(1, 2, 20, 1, "2019/02/15", 2),
(2, 2, 30, 2, "2019/09/16", 6),
(4, 3, 0.58, 3, "2019/01/16", 4),
(6, 1, 1.25, 1, "2019/09/16", 6);
