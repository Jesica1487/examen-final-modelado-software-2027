# Parte 3: Notas para Defensa Oral

## Presentacion del Proyecto

- Nombre del proyecto: Busqueda de Articulos
- Feature principal: el usuario busca por nombre de articulo o palabra clave
- Arquitectura general: arquitectura de capas, modelo MVC( MODELO VISTA CONTROLADOR)

## Decisiones de Diseno

- Estructura de clases:
- Uso de MVC: el modelo vista controlador, nos permite generar una Vista para el usuario agradable (VISOR). El modelo que es quien accede a la base de datos. El controlador es el intermediario entre los requisitos del usuario y la base de datos del sistema.
- Patrones identificados:

## Defensa del Caso de Uso

- Que funcionalidad modele: Busqueda de Articulos
- Que clases agregue: usuario, articulo, gestor_busqueda, base de datos, historial.
- Como se relacionan: el usuario realiza se registra en el sistema, y realizar el pedido de articulo en el gestor de busquda. El sistema ingresa a la base de datos y busca el articulo en los registros. En caso que exista el articulo es devuelvo al usuario y queda guardo en su historial. 

## Conceptos a Repasar

- Actor primario y secundario
- Precondicion y postcondicion
- Diferencia entre diagrama de clases y secuencia
- Principios SOLID basicos
