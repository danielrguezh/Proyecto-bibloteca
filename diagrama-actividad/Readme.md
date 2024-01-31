# Diagrama- Actividad

## Índice
- [Diagrama de actividad para el  C.U. 1](#cu-1-buscar-libro)
- [Diagrama de actividad para el C.U. 2](#cu-2-prestar-libro)
- [Diagrama de actividad para el C.U. 3](#cu-3-devolver-libro)
- [Diagrama de actividad para el C.U. 4](#cu-4-seleccionar-libro)
- [Diagrama de actividad para el C.U. 5](#cu-5-dejar-comentario)
- [Diagrama de actividad para el C.U. 6](#cu-6-ver-lista-libros)
- [Diagrama de actividad para el C.U. 7](#cu-7-registrar-usuario)
- [Diagrama de actividad para el C.U. 8](#cu-8-agregar-libro)
- [Diagrama de actividad para el C.U. 9](#cu-9-gestionar-reserva-libro)
- [Diagrama de actividad para el C.U. 10](#cu-10-buscar-por-título)
- [Diagrama de actividad para el C.U. 11](#cu-11-buscar-por-autor)
- [Diagrama de actividad para el C.U. 12](#cu-12-buscar-por-categoría)
- [Diagrama de actividad para el C.U. 13](#cu-13-visualizar-información)
- [Diagrama de actividad para el C.U. 14](#cu-14-modificar-información)

***
### C.U. 1 Buscar Libro
```mermaid
graph TD;
    Inicio --> VerificarUsuario;
    VerificarUsuario --No --> Fin;
    VerificarUsuario --Si -->
    BuscarLibro;
    BuscarLibro --> BuscarPorTítulo;
    BuscarLibro --> BuscarPorAutor;
    BuscarLibro --> BuscarPorCategoría;
    BuscarPorCategoría --> VerListaLibros;
    BuscarPorTítulo --> SeleccionarLibro;
    BuscarPorAutor --> SeleccionarLibro;
    VerListaLibros --> SeleccionarLibro;
    SeleccionarLibro --> Fin;
```
### C.U. 2 Prestar Libro
```mermaid
graph TD;
    Inicio --> SeleccionarLibro;
    SeleccionarLibro --No --> SeleccionarLibro;
    SeleccionarLibro --Si --> PrestarLibro;
    PrestarLibro --> VerificarStock
    VerificarStock -- Disponible--> ConfirmarPrestamo;
    VerificarStock --No Disponible--> DenegarPrestamo
    DenegarPrestamo --> Fin
    ConfirmarPrestamo -->
    Fin; 
```
### C.U. 3 Devolver Libro
```mermaid
graph TD;
     Inicio --> VerificarUsuario;
    VerificarUsuario --No --> Fin;
    VerificarUsuario --Si -->  DevolverLibro;
    DevolverLibro --> VerificarFecha
    VerificarFecha --Cumple con plazo --> ConfirmarDevolución;
    VerificarFecha --NO cumple con plazo --> Multa
    Multa --> ConfirmarDevolución
    ConfirmarDevolución -->
    Fin; 
```

### C.U. 4 Seleccionar Libro
```mermaid
graph TD;
    Inicio --> BuscarLibro;
    BuscarLibro --No --> BuscarLibro;
    BuscarLibro --Si --> 
    SeleccionarLibro 
    SeleccionarLibro --> Fin 
```

### C.U. 5 Dejar Comentario
```mermaid
graph TD;
    Inicio --> RegistrarUsuario
    RegistrarUsuario -- No --> RegistrarUsuario
    RegistrarUsuario -- Si --> SeleccionarLibro;
    SeleccionarLibro --Si--> Comentario;
    SeleccionarLibro --No --> SeleccionarLibro
    Comentario -->
     Fin 
```

### C.U. 6 Ver Lista Libros
```mermaid
graph TD;
    Inicio --> BuscarLibro;
    BuscarLibro --No -->
    BuscarLibro 
    BuscarLibro --> BuscarPorCategoría
    BuscarPorCategoría --Si--> VerListaLibro
    BuscarPorCategoría --No --> BuscarLibro
    VerListaLibro --> Fin 
```

### C.U. 7 Registrar Usuario
```mermaid
graph TD;
    Inicio --> IntroducirDatos;
    IntroducirDatos --No -->
    IntroducirDatos 
    IntroducirDatos -- Si --> RegistrarUsuario
    RegistrarUsuario --> 
    VerificarUsuario --Si--> Fin
    VerificarUsuario -- No --> VerificarUsuario
```

### C.U. 8 Agregar Libro
```mermaid
graph TD;
    Inicio --> VerificarEmpleado;
    VerificarEmpleado -- Si --> ConsultarLibro;
    VerificarEmpleado -- No --> Fin
    ConsultarLibro --No -->
    ConsultarLibro;
    ConsultarLibro -- Si --> AgregarLibro;
    AgregarLibro --> Fin
```

### C.U. 9 Gestionar Reserva Libro
```mermaid
graph TD;
    Inicio --> VerificarEmpleado;
    Inicio --> VerificarUsuario
        VerificarEmpleado --> Modificar-Información-Reserva;
    VerificarEmpleado -- Si --> Mostrar-Información-Reserva;
    VerificarEmpleado -- No --> VerificarEmpleado;

    VerificarUsuario -- Si --> Mostrar-Información-Reserva;
    VerificarUsuario -- No --> VerificarUsuario;
    Mostrar-Información-Reserva --> Fin
    Modificar-Información-Reserva -->
    Fin
```

### C.U. 10 Buscar por Título
```mermaid
graph TD;
    Inicio --> VerificarUsuario;
    VerificarUsuario --No --> Fin;
    VerificarUsuario --Si -->
    BuscarLibro;
    BuscarLibro --> BuscarPorTítulo;
    BuscarPorTítulo --> SeleccionarLibro;
    SeleccionarLibro --> Fin;
```

### C.U. 11 Buscar por Autor
```mermaid
graph TD;
    Inicio --> VerificarUsuario;
    VerificarUsuario --No --> Fin;
    VerificarUsuario --Si -->
    BuscarLibro;
    BuscarLibro --> BuscarPorAutor;
    BuscarPorAutor --> SeleccionarLibro;
    SeleccionarLibro --> Fin;
```


### C.U. 12 Buscar por Categoría
```mermaid
graph TD;
    Inicio --> VerificarUsuario;
    VerificarUsuario --No --> Fin;
    VerificarUsuario --Si -->
    BuscarLibro;
    BuscarLibro --> BuscarPorCategoría;
    BuscarPorCategoría --> VerListaLibros;
    VerListaLibros --> SeleccionarLibro;
    SeleccionarLibro --> Fin;
```
### C.U. 13 Visualizar Información
```mermaid
graph TD;
    Inicio --> VerificarEmpleado;
    Inicio --> VerificarUsuario
    VerificarEmpleado -- Si --> Mostrar-Información-Reserva;
    VerificarEmpleado -- No --> VerificarEmpleado;

    VerificarUsuario -- Si --> Mostrar-Información-Reserva;
    VerificarUsuario -- No --> VerificarUsuario;
    Mostrar-Información-Reserva --> Fin
```

### C.U. 14 Modificar Información
```mermaid
graph TD;
    Inicio --> VerificarEmpleado;
    VerificarEmpleado --> Modificar-Información-Reserva;
    VerificarEmpleado -- No --> VerificarEmpleado;
    Modificar-Información-Reserva -->
    Fin
```
