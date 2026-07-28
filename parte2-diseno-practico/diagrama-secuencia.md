# Parte 2: Diagrama de Secuencia

Diagrama de secuencia, nos muestra la pelicula del caso de uso. Como y en que orden se van a ejecutar las tareas.

Se adjunto codigo de diagrama, hecho en PLANTUML, para ser visualizado.

@startuml
autonumber
skinparam BoxPadding 10
skinparam ParticipantPadding 10

actor "Visitante / Usuario" as Usuario
participant ":Sistema" as Sistema
database "Base de Datos" as DB

== Registro e Inicio de Búsqueda ==
Usuario -> Sistema: Ingresa al sistema / Se registra
loop Búsqueda de Artículos
    Usuario -> Sistema: Solicita búsqueda (título o palabra clave)
    
    alt FA1: Falta criterio de búsqueda
        Sistema --> Usuario: Muestra cartel de advertencia (Requisito mínimo faltante)
    else Búsqueda Válida
        Sistema -> DB: Consulta artículos (por título o palabra clave)
        DB --> Sistema: Retorna resultados
        
        alt Artículo Encontrado
            Sistema --> Usuario: Mensaje "Encontrado" + Muestra el Artículo
            Sistema -> DB: Guarda el artículo en el historial del usuario
        else FA2: Artículo No Encontrado
            Sistema --> Usuario: Mensaje "No encontrado"
        end
    end
    
    Sistema --> Usuario: ¿Necesita otro artículo? (Sí / No)
end

== Fin del Caso de Uso ==
Usuario -> Sistema: Finaliza uso
@enduml
        
    
  
