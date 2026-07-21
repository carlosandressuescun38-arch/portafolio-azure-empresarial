# A3 — Maquina Virtual Basica (IaaS)

## Certificacion
AZ-900 (Azure Fundamentals)

## Concepto demostrado
Diferencia entre IaaS (Infrastructure as a Service) y PaaS (Platform as a Service).
En IaaS, el usuario administra el sistema operativo, actualizaciones, seguridad del SO
y escalado manual. En PaaS (como el App Service usado en P2), Azure administra el
runtime y el sistema operativo subyacente, el usuario solo administra la aplicacion.

## Accion realizada
Se creo una VM Ubuntu Server 24.04 LTS, tamano B1s (servicios gratuitos elegibles),
en Mexico Central, dentro de un Resource Group dedicado.

## Problema resuelto durante la ejecucion
El primer intento de creacion fallo porque se selecciono por error la imagen
"Ubuntu Pro 20.04 LTS", una oferta de pago de Canonical no cubierta por creditos
de Azure for Students. Se corrigio seleccionando "Ubuntu Server 24.04 LTS" (sin Pro),
que es la imagen base gratuita, cubierta completamente por el computo de Azure.

## Comparacion IaaS vs PaaS

| Aspecto | IaaS (esta VM) | PaaS (App Service, P2) |
|---|---|---|
| Gestion del SO | Responsabilidad del usuario | Gestionado por Azure |
| Parches de seguridad | Manual | Automatico |
| Escalado | Manual (cambiar tamano de VM) | Automatico (scale out/up) |
| Control | Total sobre el entorno | Limitado al codigo de la app |
| Velocidad de despliegue | Mas lenta (requiere configuracion de SO) | Mas rapida (solo se despliega codigo) |

## Gestion de costos
La VM se detuvo inmediatamente (estado Stopped/deallocated) tras capturar evidencia.
El Resource Group completo se elimino tras documentar, dejando cero recursos activos.

## Evidencia
Ver /evidence