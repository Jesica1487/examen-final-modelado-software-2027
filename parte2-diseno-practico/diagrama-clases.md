# Parte 2: Diagrama de Clases

el diagrama de clases, permite ver la estructura logica del sistema. Muestra los elementos que necesitamos para construir.

DIAGRAMA HECHO  EN PLANTUML, se adjunta el codigo, para ser visualizado.


@startuml
' Configuraciones visuales
skinparam classAttributeIconSize 0
skinparam linetype ortho

class Usuario {
    + idUsuario : int
    + nombreUsuario : String
    + email : String
    + contrasena : String
    + registrar() : void
    + iniciarSesion() : void
    + decidirNuevaBusqueda() : boolean
}

class Articulo {
    + idArticulo : int
    + titulo : String
    + contenido : String
    + palabrasClave : String
    + fechaPublicacion : Date
    + obtenerDetalles() : String
}

class Historial {
    + idHistorial : int
    + fechaConsulta : Date
    + registrarBusqueda(articulo: Articulo) : void
    + obtenerHistorial() : List<Articulo>
}

class GestorBusqueda {
    + validarRequisitos(termino: String) : boolean
    + buscarArticulo(termino: String) : List<Articulo>
    + mostrarAlerta(mensaje: String) : void
    + solicitarContinuidad() : boolean
}

class BaseDeDatos {
    + ejecutarConsulta(query: String) : List<Object>
    + guardarRegistro(dato: Object) : void
}

' Relaciones estructurales
Usuario "1" --> "1" GestorBusqueda : interactúa >
Usuario "1" *-- "1" Historial : compone >
Historial "*" o-- "1" Articulo : referencia >
GestorBusqueda "1" --> "1" BaseDeDatos : consulta >
BaseDeDatos "1" --> "*" Articulo : almacena >

@enduml






