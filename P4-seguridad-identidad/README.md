# P4 — Seguridad e Identidad (Zero Trust)

## Certificacion
AZ-500 (Azure Security Engineer Associate)

## Objetivo
Eliminar credenciales hardcodeadas mediante Key Vault + Managed Identity, aplicando principio de minimo privilegio (RBAC).

## Arquitectura
Web App (P2) --Managed Identity--> Key Vault (kv-p4-mejpppk2fksre) --secret--> sql-admin-password

## Componentes desplegados
| Recurso | Nombre | Proposito |
|---|---|---|
| Key Vault | kv-p4-mejpppk2fksre | Almacenamiento centralizado de secretos |
| Managed Identity | Principal ID: adef8317-1a78-451d-bbe9-d0eb02bcdf4c | Identidad de la Web App sin credenciales compartidas |
| Rol RBAC | Key Vault Secrets User | Acceso de solo lectura, minimo privilegio |

## Decisiones de diseno
- RBAC en vez de Access Policies (legacy): modelo recomendado actual de Azure.
- System-assigned Managed Identity: ciclo de vida gestionado automaticamente por Azure.
- Scope del rol limitado al Key Vault especifico, no a nivel de suscripcion.

## Resultado medible
- 1 credencial critica migrada de texto plano a Key Vault gestionado.
- 0 claves de acceso compartidas.
- Acceso auditable via Azure AD sign-in logs.

## Evidencia
Ver /evidence