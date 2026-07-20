# P2 — Arquitectura Tres Capas (App Service + Azure SQL)

## Certificacion
AZ-204 (Azure Developer Associate)

## Objetivo
Demostrar despliegue de arquitectura PaaS estandar empresarial mediante IaC (Bicep).

## Arquitectura
Web App (App Service, tier Free) -> Azure SQL Database (Serverless, auto-pause 60 min)

## Decisiones de diseno
- SQL Serverless con auto-pause: optimizacion de costos en cuenta con creditos limitados.
- Firewall rule AllowAzureServices: acceso restringido, sin exposicion publica amplia.
- Region brazilsouth: unica region de LATAM permitida por Azure Policy de la suscripcion estudiantil.

## Recursos desplegados
- App Service Plan: app-p2-3tier-mejpppk2fksre-plan
- Web App: app-p2-3tier-mejpppk2fksre
- SQL Server: app-p2-3tier-mejpppk2fksre-sql
- SQL Database: app-p2-3tier-mejpppk2fksre-db

## Outputs
- Web App URL: https://app-p2-3tier-mejpppk2fksre.azurewebsites.net
- SQL FQDN: app-p2-3tier-mejpppk2fksre-sql.database.windows.net

## Deuda tecnica identificada (resuelta en P4)
Password SQL pasado en texto plano en el comando de deployment -> migrado a Key Vault.

## Evidencia
Ver /evidence