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


### ENDPOINTS

**USUARIO**
Get Usuarios - Obtener todos los usuarios
Get idUsuario - Buscar usuario por idUsuario
Get Username - Buscar usuario por Username
Get UserDNI - Buscar un usuario por DNI
Get UserTlfn - Buscar un usuario por su teléfono
Get UserEmail - Buscar un usuario por email
Get UserRol - Buscar usuario por rol
Get idVisita - Buscar usuario por idVisita
Post Usuario - Introduce un nuevo usuario
Put Usuario - Actualizar datos de usuario
Delete Usuario - Eliminar usuario

**VISITAS**
Get Visitas - Obtener todas las visitas
Get idVisitas - Buscar visitas por idVisita
Get idVisitas - Buscar visitas por idVehiculo
Get FechaVisita - Buscar visitas por fecha
Put MotivoVisita - Actualiza el motivo de un visita existente
Delete Visita - Elimina una visita existente

**VEHÍCULO**
Get Vehiculos - Obtener todos los vehiculos
Get idVehiculo - Buscar vehículos por idVehiculo
Get idUsuario - Buscar vehículos por idUsuario
Get Marca - Buscar vehículos por marca
Post Vehiculo - Introduce un nuevo vehículo
Put Vehiculo - Actualiza un vehículo existente
Delete Vehículo - Elimina un vehículo existente


### LÓGICA DE NEGOCIO: **************
Obtener todos los usuarios, visitas y vehículos.
Buscar usuario por idUsuario, Username, DNI, teléfono, email, rol e idVisita.
Insertar nuevo usuario.
Actualizar datos de usuario.
Eliminar usuario.
Buscar visitas por idVisita, idVehiculo y fecha.
Actualizar el motivo de un visita existente.
Eliminar una visita existente.
Buscar vehículos por idVehiculo, idUsuario y marca.
Insertar un nuevo vehículo.
Actualizar un vehículo existente.
Elimina un vehículo existente.


### EXCEPCIONES: **************
**ÉXITO:**
OK : 200 -> Operación correcta
Created : 201 -> Inserción exitosa
No content : 204 -> Eliminación exitosa

**ERRORES:**
BadRequest : 400 -> Solicitud incorrecta
NotAuthorization: 401 -> Sin autorización
NotFound : 404 -> Recurso no encontrado
Duplicate : 409 -> Recurso duplicado
APIHandler : 400, 404, 500 -> Múltiples errores en la API


### RESTRICCIONES DE SEGURIDAD: **************
SecurityFilterChain(HttpSecurity http): Configura los filtros de seguridad para deshabilitación de CSRF y  usar la autenticación con JWT
passwordEncoder(): Codificación segura de contraseñas con BCrypt.
authenticationManager(AuthenticationConfiguration authenticationConfiguration): Manejador central de autenticaciones.
jwtEncoder(): Codificación de tokens JWT utilizando las claves RS.
jwtDecoder(): Decodificación de tokens JWT utilizando la clave pública RSA.
