```mermaid
graph TD;
    Permisos[Permisos]
    Roles[Roles]
    RolesPermisos[RolesPermisos]
    Personas[Personas]
    Usuario[Usuario]
    Servicios[Servicios]
    TipoHabitacion[TipoHabitacion]
    Habitaciones[Habitaciones]
    Paquetes[Paquetes]
    PaqueteServicio[PaqueteServicio]
    Reservas[Reservas]

    Permisos -->|IdPermisos| RolesPermisos
    Roles -->|IdRol| RolesPermisos
    Personas -->|IdPersona| Usuario
    Roles -->|IdRol| Usuario
    Servicios -->|IdServicios| Paquetes
    Habitaciones -->|IdHabitacion| Paquetes
    Servicios -->|IdServicios| PaqueteServicio
    Paquetes -->|IdPaquetes| PaqueteServicio
    Paquetes -->|IdPaquetes| Reservas
    TipoHabitacion -->|IdTipoHabita| Habitaciones

    %% Relaciones con rombos
    RolesPermisos -->|tiene| Roles
    RolesPermisos -->|tiene| Permisos
    Usuario -->|tiene| Personas
    Paquetes -->|contiene| Servicios
    Paquetes -->|contiene| Habitaciones
    PaqueteServicio -->|ofrece| Servicios
    Habitaciones -->|es de tipo| TipoHabitacion
    Habitaciones -->|pertenece a| TipoHabitacion
