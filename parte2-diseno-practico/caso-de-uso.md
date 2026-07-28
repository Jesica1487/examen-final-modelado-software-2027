# Parte 2: Caso de Uso
Opcion A: Busqueda de Articulos

Requisito: "Agregar funcionalidad de 'Buscar articulos por titulo o palabra clave' para todos los visitantes"


**ID: CU-01 *  
**Nombre: BUSQUEDA DE ARTICULOS**

**Actor Principal: VISITANTE**  
**Actores Secundarios: BASE DE DATOS**

## Descripcion
 Los visitantes y usuarios pueden buscar articulos ingresando terminos en una barra de busqueda. El sistema devuelve los articulos cuyo titulo o contenido coincida parcial o totalmente con el termino buscado, ordenados por relevancia o fecha de publicacion

## Precondiciones:
EL USUARIO DEBE TENER UN USUARIO CARGADO.


## Flujo Principal

1. EL usuario se registra en el sistema
2.  el usuario inicia la busqueda del articulo, con la opcion de titulo o palabra clave.
3.  el sistema, realiza la busqueda del articulo.
4.  el sistema devuelve un mensaje como "encontrado" y el articulo solicitado.
5.  el sistema devuelve un mensaja como "no encontrado" si no existe en la base de datos y vuelve al paso 2.
6.  el sistema muestra mensaje si el usuario necesita otro articulo, en caso que la respuesta sea positiva vuelve al paso 2.
7.  en caso que el usuario no tenga otra busqueda, el sistema vuelve al paso 1.
8.  fin del caso de uso  

## Flujos Alternativos

### FA1
si el sistema detecta que no esta el requisito mínimo del paso 2, muestra un cartel de advertencia al usuario.
### FA2

## Postcondiciones
el articulo solicitado queda guardado en el historial del usuario. De esta manera lo tendrá disponible cuando se loguee nuevamente.

-
