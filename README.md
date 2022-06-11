# Bases2_Proyecto1
Proyecto 1 de Sistema de bases 2, vacaciones junio 2022


# ***Instalación de Oracle*** #

Pasos para la instlacion de oracle


+ Paso 1

<p align=center>
	 <img src="./Images/instal1.PNG" alt="" width=60%>
</p>


+ Paso 2

<p align=center>
	 <img src="./Images/instal2.PNG" alt="" width=60%>
</p>

+ Paso 3

<p align=center>
	 <img src="./Images/instal3.png" alt="" width=60%>
</p>

+ Paso 4

<p align=center>
	 <img src="./Images/instal4.PNG" alt="" width=60%>
</p>

+ Paso 5

<p align=center>
	 <img src="./Images/instal5.PNG" alt="" width=60%>
</p>

+ Paso 6

<p align=center>
	 <img src="./Images/instal6.PNG" alt="" width=60%>
</p>


# ***Comandos de configuración*** #

Los siguientes comando se ejecutan en SQL Plus:

+ Comando para conectarnos como SYSDBA

> CONN /AS SYSDBA

para la contraseña solo presionamos enter

<p align=center>
	 <img src="./Images/conf1.png" alt="" width=80%>
</p>



+ Cambio de sesión

> ALTER SESSION SET "_ORACLE_SCRIPT"=TRUE;

+ Creación del TableSpace

```
CREATE TABLESPACE ELECCIONESTBS
DATAFILE 'C:/db/ELECCIONESDTF.tbs' 
SIZE 250M 
AUTOEXTEND ON next 10 M
MAXSIZE 500M;
```

+ Creaación de usuario manager con default tablespace y asignación de rol DBA

> CREATE USER MANAGER IDENTIFIED BY manager DEFAULT TABLESPACE ELECCIONESTBS TEMPORARY TABLESPACE TEMP;

> GRANT DBA TO MANAGER;

# ***Conexión con SQL DEVELOPER*** #

+ Paso 1

<p align=center>
	 <img src="./Images/developer1.png" alt="" width=50%>
</p>

+ Paso 2

<p align=center>
	 <img src="./Images/developer2.png" alt="" width=80%>
</p>

# ***Creación de tablas e inserción de datos*** #

Para la creación de tablas se ejecutó el archivo:
+ Script Autenticacion

Para la inserción de datos se ejecutó el archivo:
+ Example data

# ***Creación de usuarios y asignación de permisos*** #

+ Creación de usuarios

```
CREATE USER guest1 IDENTIFIED BY guest1 DEFAULT TABLESPACE ELECCIONESTBS TEMPORARY TABLESPACE TEMP;
CREATE USER guest2 IDENTIFIED BY guest2 DEFAULT TABLESPACE ELECCIONESTBS TEMPORARY TABLESPACE TEMP;
CREATE USER guest3 IDENTIFIED BY guest3 DEFAULT TABLESPACE ELECCIONESTBS TEMPORARY TABLESPACE TEMP;

CREATE USER mesas1 IDENTIFIED BY mesas1 DEFAULT TABLESPACE ELECCIONESTBS TEMPORARY TABLESPACE TEMP;
CREATE USER mesas2 IDENTIFIED BY mesas2 DEFAULT TABLESPACE ELECCIONESTBS TEMPORARY TABLESPACE TEMP;
CREATE USER mesas3 IDENTIFIED BY mesas3 DEFAULT TABLESPACE ELECCIONESTBS TEMPORARY TABLESPACE TEMP;
CREATE USER mesas4 IDENTIFIED BY mesas4 DEFAULT TABLESPACE ELECCIONESTBS TEMPORARY TABLESPACE TEMP;

CREATE USER it1 IDENTIFIED BY it1 DEFAULT TABLESPACE ELECCIONESTBS TEMPORARY TABLESPACE TEMP;
CREATE USER it2 IDENTIFIED BY it2 DEFAULT TABLESPACE ELECCIONESTBS TEMPORARY TABLESPACE TEMP;
CREATE USER it3 IDENTIFIED BY it3 DEFAULT TABLESPACE ELECCIONESTBS TEMPORARY TABLESPACE TEMP;

CREATE USER admin1 IDENTIFIED BY admin1 DEFAULT TABLESPACE ELECCIONESTBS TEMPORARY TABLESPACE TEMP;
CREATE USER admin2 IDENTIFIED BY admin2 DEFAULT TABLESPACE ELECCIONESTBS TEMPORARY TABLESPACE TEMP;
```

+ Asignación de permisos

```
GRANT CREATE SESSION TO guest1, guest2, guest3, mesas1, mesas2, mesas3, mesas4, it1, it2, it3, admin1, admin2;
GRANT SELECT ANY TABLE TO guest1, guest2, guest3, mesas1, mesas2, mesas3, mesas4, it1, it2, it3, admin1, admin2;
GRANT INSERT ANY TABLE TO mesas1, mesas2, mesas3, mesas4, admin1, admin2;
GRANT UPDATE ANY TABLE TO admin1, admin2;
GRANT DELETE ANY TABLE TO admin1, admin2;
GRANT CREATE USER TO it1, it2, it3, admin1, admin2;
GRANT CREATE TABLE TO it1, it2, it3;
```
