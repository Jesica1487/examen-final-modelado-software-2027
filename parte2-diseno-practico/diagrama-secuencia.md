# Parte 2: Diagrama de Secuencia

Diagrama de secuencia, nos muestra la pelicula del caso de uso. Como y en que orden se van a ejecutar las tareas.

Se adjunto codigo de diagrama, hecho en PLANTUML, para ser visualizado.

@startuml
' Configuraciones visuales (opcional, para que se vea más profesional)
skinparam style strictuml
skinparam SequenceMessageAlignment center

autonumber
actor Usuario
participant Sistema
database BaseDeDatos

Usuario -> Sistema: Registra / Inicia sesión (Paso 1)
activate Sistema

loop Búsqueda de artículos

    Usuario -> Sistema: Inicia búsqueda por título/palabra clave (Paso 2)
    
    alt Requisito mínimo NO cumplido (FA1)
        Sistema --> Usuario: Muestra cartel de advertencia
    else Requisito cumplido
        Sistema -> BaseDeDatos: Consulta artículo (Paso 3)
        activate BaseDeDatos
        
        alt Artículo encontrado
            BaseDeDatos --> Sistema: Retorna artículo
            Sistema --> Usuario: Mensaje "Encontrado" y muestra artículo (Paso 4)
            Sistema -> BaseDeDatos: Guarda en historial del usuario (Postcondición)
        else Artículo no encontrado
            BaseDeDatos --> Sistema: Retorna vacío
            Sistema --> Usuario: Mensaje "No encontrado" (Paso 5)
        end
        deactivate BaseDeDatos
    end
    
    Sistema -> Usuario: ¿Necesita buscar otro artículo? (Paso 6)
    Usuario --> Sistema: Responde Sí/No
end

Usuario -> Sistema: Indica no tener más búsquedas
Sistema --> Usuario: Vuelve a pantalla de inicio (Paso 7)
deactivate Sistema

note right of Usuario: Fin del caso de uso (Paso 8)
@enduml
