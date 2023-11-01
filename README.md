# Parcial 2 - Cine Para Todos

## David Dulce - A00398802

## Ingeniería de Software II

El cine "CineParaTodos" busca implementar un sistema de reservas en línea para optimizar la experiencia del cliente y facilitar la gestión de las funciones. El objetivo es permitir a los espectadores reservar boletos para proyecciones específicas y, al mismo tiempo, proporcionar al personal del cine una herramienta para administrar las reservas y la asistencia de manera eficiente.

## Requerimientos

| ID | Descripción |
| --- | --- |
| R1 | Registro de Usuarios |
| R2 | Rservación de Boletos |
| R3 | Confirmación de reservas |
| R4 | Gestión de Reservas por el Personal |
| R5 | Ventas de Alimentos y Bebidas |
| R6 | Notificaciones y Recordatorios |
| R7 | Historial de Reservas |
| R8 | Calificaciones y Comentarios |

Notas:

- Para el R6, se asume que los mensajes son vía email

## 1 - Sistema

- Usuarios

  - Registro

  - Puntos

  - Información de Usuarios

- Email

- Funciones

  - Asistencia

  - Información de Funciones

- Reservas

- Ventas

  - Pagos

  - Alimentos y Bebidas

- Calificaciones

## 2 - Asignación de Requerimientos

| ID | Información de Usuarios | Registro | Puntos | Email | Información de Funciones | Asistencia | Reservas | Pagos | Alimentos y Bebidas | Calificaciones |
| -- | -- | -- | -- | -- | -- | -- | -- | -- | -- | -- |
| R1 | X | X | X |
| R2 | | X | X | X | X |
| R3 | | | X | X | | | X | X |
| R4 | | | | X | X | | X |
| R5 | | | | | | | | X | X |
| R6 | X | | | X | X | | X |
| R7 | | | | | | | X |
| R8 | | | | | | | | | | X |

## 3 - Subespecificación
Mi cédula termina en 5, por lo tanto debo especificar el R2 - Hacer Rservas

Los usuarios registrados deben poder seleccionar la película que desean ver, la fecha y la hora de la proyección. De acuerdo con el horario que eligen ver la película, se asignarán puntos diferentes al usuario así: 
SI el horario es a partir de las 4pm – Se asignan 50 puntos por boleta vendida
Si el horario es antes de esa hora – se asignan 35 puntos por boleta.
El sistema debe mostrar la disponibilidad de asientos para la película, fecha y hora seleccionados.
Los clientes deben poder elegir el número de boletos que desean reservar.

Este requerimiento tiene las siguientes funcionalidades o acciones:

- Seleccionar: Película, Fecha, Hora

- Asignar puntos:

  hora de inicio >= 4pm -> 50 puntos / boleta

  hora de inicio < 4pm -> 35 puntos / boleta

- Mostrar disponibilidad de asientos

- Elegir número de boletos

Entonces estos serán los subrequerimientos:

| ID | Nombre | Descripción |
| -- | -- | -- |
| R2.1 | Seleccionar Película | Se trae la infromación de las funciones para tener las funciones y horarios (fecha y hora) disponibles. |
| R2.2 | Asignar puntos | Si la función empieza después de las 16:00 se asignan 50 puntos, si empieza antes, se asignan 35 puntos.  |
| R2.3 | Mostrar disponibilidad de asientos | Se trae la información de la función y se muestra la disponibilidad de asientos. |
| R2.4 | Elegir número de boletos | Se elige el número de boletos que se desean reservar. |

La asignación req/sistema luce asì:

| ID | Información de Usuarios | Registro | Puntos | Email | Información de Funciones | Asistencia | Reservas | Pagos | Alimentos y Bebidas | Calificaciones |
| -- | -- | -- | -- | -- | -- | -- | -- | -- | -- | -- |
| R2.1 | | | | | X
| R2.2 | | | X | | | | | | | |
| R2.3 | | | | | X | | | | | |
| R2.4 | | | | | | | X | | | |

Notas:

- Estoy asumiendo que después de elegir el número de boletos, la información de la reserva se envía al sistema de Reservas para confirmarla con las especificaciones del R3.

- NO se necesita particionar de nuevo para **este** requerimiento.

## Formato bicolumnar

| ID | 1 |
| -- | -- |
| Author | David Dulce |
| Use Case | Registrar Usuario |
| Related Use Cases | Enviar email |
| Actor | Nuevo Cliente |
| Precondition | El usuario no está registrado aún |
| Context |  |
| User Actions | System Actions* |
| Ingresar datos | Validar que el usuario no exista, añadir a base de datos como no confirmado, enviar email de confirmación |
| Postcondition | El usuario queda pendiente de confirmar su registro vía email |
| Notes | Si está registrado, mostrar la pantalla de iniciar sesión. |

***: Including normal flow and exceptions.**
