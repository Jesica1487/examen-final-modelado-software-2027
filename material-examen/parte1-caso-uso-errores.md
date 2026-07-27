# Parte 1 del Examen: Analisis Critico

**Tiempo:** 20 minutos  
**Puntaje:** 20% del examen final

---

## Consigna

A continuacion se presenta un caso de uso con **7 errores intencionales**. Tu tarea es:

1. Identificar minimo 5 errores
2. Explicar por que es un error
3. Proponer la correccion apropiada

Usa este formato:

```text
ERROR #1:
Ubicacion: [Seccion donde esta el error]
Descripcion: [Que esta mal]
Correccion: [Como deberia ser]
```

---

## Caso de Uso con Errores

### CU-10: Registrar Usuario

**Actor Principal:** Base de Datos, Visitante

ERROR 1_
UBICACION: ACTOR PRINCIPAL
DESCRIPCION: LA base de datos no puede ser un actor
CORRCCION: el actor principal es el visitante o usuario.

**Descripcion:**  
La base de datos permite que un visitante se registre en la plataforma creando una cuenta de usuario.

**Precondiciones:**
- El visitante debe tener una invitacion de otro usuario registrado
- El visitante debe haber visitado al menos 5 articulos en los ultimos 30 dias

ERROR 2_
UBICACION: PRECONDICION
DESCRIPCION: EL VISITANTE DEBE TENER UNA INVITACION.
CORRCCION: es un requisito innecesario, no debe ser un condicional. Las condiciones precondiciones deben ser estados necesarios para ejecutar el caso de uso, no restricciones.

**Flujo Principal:**
1. El Visitante accede a la pagina de registro
2. El sistema muestra el formulario con campos: nombre, email, contraseña y biografia
3. El Visitante completa todos los campos del formulario
4. El Visitante hace clic en "Crear cuenta"
5. El sistema guarda la informacion inmediatamente
6. El sistema muestra mensaje "Cuenta creada con exito"
7. Fin del caso de uso

ERROR 3_   
UBICACION: FLUJO PRINCIPAL
DESCRIPCION: el sistema no pide confirmacion de datos antes de finalizar
CORRECCION: debemos crear un paso posterior al numero 4, con este confirmar antes de crear cuenta.

**Flujos Alternativos:**
- Ninguno

ERROR 4_
UBICACION: FLUJOS ALTERNATIVOS
DESCRIPCION: siempre debe haber un flujo alternativo, por ejemplo " el usuario cancela la eliminacion de datos"
CORRECCION: debemos agregar este paso, posterior al paso 3, si el usuario no decide cancelar la carga de los datos, el sistema debe retornar al paso 2, con un mensaje "carga de datos cancelada".

**Postcondiciones:**
- La cuenta queda registrada en la base de datos
- Se envia un email de notificación a todos los usuarios de la plataforma
- Se crea automáticamente un articulo de bienvenida en nombre del nuevo usuario
- El sistema inicia sesión automáticamente con la nueva cuenta

**Excepciones:**
- Si el email ya existe en el sistema, el registro se ignora sin mostrar ningun mensaje

ERROR 5_
UBICACION: SI EL MAIL YA EXISTE EN EL SISTEMA, EL REGISTRO IGNORA SIN MOSTRAR NINGUN MENSAJE
DESCRIPCION:el mail es parte de los requisitos, por lo que debe ser unico por usuario.
CORRECCION: en caso que el mail ya exista, el sistema tiene que generar un mensaje posterior al paso 2, dando aviso del requisito pendiente.
---

## Recordatorio

Busca errores en:
- Actores
- Precondiciones
- Flujo principal
- Flujos alternativos
- Postcondiciones
- Excepciones
