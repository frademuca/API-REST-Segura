# API-REST-Segura
Proyecto final del primer trimestre DWES

## NOMBRE: GESTIÓN DE USUARIOS DE UN TALLER DE MECÁNICA

### IDEA:
API Rest para la gestión de usuarios (tanto clientes como mecánicos) de un taller de mecánica. Se podrán consultar los datos de dichos usuarios, los vehículos y las visitas asociadas a ambos. Constará de 3 tablas; usuario, visitas y vehículo.

### JUSTIFICACIÓN:
La aplicación permitirá gestionar los clientes y empleados de un taller de mecánica, a su vez de los vehículos y el historial de visitas/reparaciones.

### TABLAS DEL PROYECTO
**USUARIO**
idUsuario - int [Autoincrement, Primary Key]
Username - String [Unique, Not null]
Password - String [Not null]
Roles - String [Not null]
Nombre - String [Not null]
Apellidos - String [Not null]
DNI - String [Not null]
Dirección - String
Teléfono - String
Email  - String
Rol - Boolean [Not null]
idVisita - int [Autoincrement, Foreign Key]
**VISITAS**
idVisita  - int [Autoincrement, Primary Key]
idVehiculo  - int [Autoincrement, Foreign Key]
Fecha visita - Date [Not null]
Motivo visita- String [Not null]
**VEHÍCULO**
idVehiculo  - int [Autoincrement, Primary Key]
idUsuario - int [Autoincrement, Foreign Key]
Marca - String [Not null]
Modelo - String [Not null]
Motorización - String [Not null]
Año - String [Not null]
