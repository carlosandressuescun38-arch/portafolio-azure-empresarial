# A5 — Explorar RBAC y Azure Policy

## Certificacion
AZ-900 (Azure Fundamentals)

## Concepto demostrado
RBAC (Role-Based Access Control) y Azure Policy son mecanismos de gobernanza
distintos pero complementarios:
- RBAC controla QUIEN puede hacer QUE accion sobre un recurso (autenticacion/autorizacion).
- Azure Policy controla QUE configuraciones son permitidas, independientemente de quien
  las intente aplicar (cumplimiento y estandares organizacionales).

## Accion realizada
Se exploro (sin modificar) la configuracion de RBAC y Policy de la suscripcion
Azure for Students:
- RBAC: usuario ca.avendanos@uniandes.edu.co con rol asignado a nivel de suscripcion.
- Policy: politica "Allowed locations" activa, restringiendo el despliegue de recursos
  unicamente a las regiones brazilsouth, mexicocentral, chilecentral, southcentralus
  y canadacentral.

## Relevancia practica
Esta politica fue descubierta durante el desarrollo real de P2 (arquitectura tres capas),
cuando un intento de despliegue en eastus fallo con error "RequestDisallowedByAzure".
Este ejercicio documenta formalmente el mecanismo que causo ese comportamiento.

## Diferencia clave (pregunta tipica de examen AZ-900)
RBAC responde: "¿Puede este usuario crear una VM?"
Azure Policy responde: "¿Puede crearse una VM en esta region/con esta configuracion,
sin importar quien lo intente?"

## Evidencia
Ver /evidence