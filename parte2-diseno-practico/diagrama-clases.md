# Parte 2: Diagrama de Clases

el diagrama de clases, permite ver la estructura logica del sistema. Muestra los elementos que necesitamos para construir.

DIAGRAMA HECHO  EN PLANTUML, se adjunta el codigo, para ser visualizado.

@startuml
skinparam classAttributeIconSize 0

class Usuario {
    - idUsuario: Integer
    - nombre: String
    - email: String
    + registrarse(): void
    + iniciarSesion(): boolean
}

class HistorialBusqueda {
    - idHistorial: Integer
    - terminoBusqueda: String
    - fechaBusqueda: Date
    + guardarBusqueda(): void
}

class Articulo {
    - idArticulo: Integer
    - titulo: String
    - contenido: String
    - fechaPublicacion: Date
    + obtenerDetalles(): String
}

class Buscador {
    - termino: String
    + buscarPorTitulo(titulo: String): List<Articulo>
    + buscarPorPalabraClave(palabra: String): List<Articulo>
}

Usuario "1" --> "0..*" HistorialBusqueda : genera >
HistorialBusqueda "1" --> "1" Articulo : referencia >
Buscador ..> Articulo : busca >
Usuario ..> Buscador : utiliza >

@enduml
