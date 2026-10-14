# PostgreSQL Advanced — proyecto empresarial de 30 horas

## Caso de negocio y secuencia

**Distribuidora Andina** vende equipos y accesorios a clientes empresariales. Su plataforma nueva se implementa en PostgreSQL; el histórico está en SQL Server. El equipo DBA debe entregar una plataforma operable, con recuperación comprobada, continuidad, acceso por región y análisis de entregas.

El temario del Excel se utiliza como referencia de contenidos y tiempos. La migración se adapta a **SQL Server**, conforme a la solicitud del curso. PostgreSQL **16**, con el parche disponible en PGDG, es la plataforma inicial; el capítulo 8 ensaya el paso a **18**. No se exige el antiguo parche 16.2.

```mermaid
flowchart LR
    C1[1. Plataforma y datos iniciales] --> C2[2. Operación]
    C2 --> C3[3. Histórico SQL Server]
    C3 --> C4[4. Respaldos y recuperación]
    C4 --> C5[5. Replicación y continuidad]
    C5 --> C6[6. Seguridad]
    C6 --> C7[7. Cobertura geográfica]
    C7 --> C8[8. Rendimiento y actualización]
```

| Capítulo y laboratorio | Capítulo completo | Práctica | Entrega que recibe el siguiente capítulo |
|---|---:|---:|---|
| [1. Introducción y arquitectura](Capitulo01/README.md) | 180 min | 100 min | Base `sales_pg`, esquema `sales` y datos iniciales |
| [2. Administración y operación](Capitulo02/README.md) | 180 min | 100 min | Configuración documentada y acceso controlado |
| [3. Migración desde SQL Server](Capitulo03/README.md) | 240 min | 120 min | Histórico conciliado e integrado |
| [4. Respaldos y recuperación](Capitulo04/README.md) | 240 min | 125 min | Restauración lógica y PITR comprobadas |
| [5. Replicación y alta disponibilidad](Capitulo05/README.md) | 240 min | 140 min | Réplica física y ensayo de réplica lógica |
| [6. Seguridad](Capitulo06/README.md) | 240 min | 100 min | Roles, TLS y aislamiento regional |
| [7. Extensiones y PostGIS](Capitulo07/README.md) | 180 min | 85 min | Consultas de cobertura y distancia |
| [8. Actualización, estadísticas y monitoreo](Capitulo08/README.md) | 300 min | 150 min | Consulta optimizada y ensayo en PostgreSQL 18 |
| **Total** | **1.800 min / 30 h** | **920 min** | **Proyecto completo** |

Los 880 minutos restantes corresponden a teoría, introducciones y discusión según el temario. Cada guía incluye fundamentos, comandos, resultados esperados, ejercicios y criterios de aceptación. La evidencia se registra en las tablas del propio README o se revisa en pantalla.

## Entorno compartido

| Equipo | Dirección privada de ejemplo | Uso |
|---|---|---|
| `pg-primary` | `192.168.56.10` | Ubuntu Server 22.04/24.04, PostgreSQL 16, puerto 5432 |
| `pg-standby` | `192.168.56.11` | Ubuntu y misma versión mayor de PostgreSQL, réplica física 5432 |
| `sql-source` | `192.168.56.20` | SQL Server 2022 Developer, solo para laboratorio |
| Estación DBA | `192.168.56.30` | SSH, SSMS y cliente PostgreSQL |
| Clústeres auxiliares | En `pg-primary` | PITR 5544; PostgreSQL 18 en 5545; analítica lógica en la misma instancia 16 |

Asigne estas IP en la red privada del hipervisor, sin sustituir la interfaz de salida a Internet. Cada nodo PostgreSQL requiere al menos 2 vCPU, 4 GB RAM y 40 GB libres; el primario necesita espacio adicional para copias y el ensayo de actualización. Verifique nombres con `getent hosts` o utilice las IP explícitas. SQL Server debe estar instalado y ser accesible desde SSMS antes del capítulo 3.

**Convenciones:** `bash` se ejecuta en Linux; `sql` en PostgreSQL dentro de `psql`; `tsql` en SSMS conectado a SQL Server. No ejecute comandos Linux en PowerShell. En `psql`, active `\set ON_ERROR_STOP on`. Los errores de permisos señalados expresamente son pruebas negativas y se ejecutan por separado.

**Archivos del curso:** solo se mantienen los nueve `README.md`. Los diagramas Mermaid son imágenes conceptuales renderizadas dentro de Markdown en GitHub; no requieren PNG, SVG ni enlaces externos. Los comandos que generan respaldos, archivos de configuración y señales de recuperación los crean **en las VM del laboratorio**, como parte de la operación del motor. Todos sus contenidos e instrucciones están documentados aquí; no se crean scripts, CSV ni archivos SQL en el repositorio.

## Contrato de datos

`customers → orders → order_items ← products` representa el mismo negocio en todos los capítulos. Los identificadores 1–3 pertenecen a la plataforma nueva; el histórico usa 101–102 para practicar una integración sin colisiones. Los importes son unidades monetarias ficticias, con precisión de dos decimales; las fechas se interpretan en UTC.

| Hito | Clientes | Productos | Pedidos | Líneas | Venta acumulada |
|---|---:|---:|---:|---:|---:|
| Capítulo 1 | 3 | 3 | 2 | 3 | 1.860,00 |
| Capítulo 3 | 5 | 5 | 4 | 6 | 2.760,00 |
| Capítulos 4–7 | 5 | 5 | 4 | 6 | 2.760,00 |

Las pruebas posteriores usan cambios revertidos o conservan el estado anterior. El capítulo 8 genera volumen en una tabla independiente `sales.performance_orders`. No elimine `sales_pg` ni promueva la réplica física en el recorrido principal.

## Registro de entrega

Complete esta tabla dentro del README al realizar el curso. No sustituya evidencia real por resultados esperados.

| Hito | Fecha UTC | Responsable | Evidencia observada | Estado |
|---|---|---|---|---|
| Plataforma | Pendiente | Pendiente | Versión, conexión y conciliación | Pendiente |
| Migración | Pendiente | Pendiente | Conteos e importes origen/destino | Pendiente |
| Recuperación | Pendiente | Pendiente | Duración y marcador recuperado | Pendiente |
| Continuidad | Pendiente | Pendiente | Estado streaming y sincronía | Pendiente |
| Seguridad | Pendiente | Pendiente | Pruebas permitidas/rechazadas | Pendiente |
| Geografía | Pendiente | Pendiente | Distancias y cobertura | Pendiente |
| Optimización | Pendiente | Pendiente | Plan antes/después y validación 18 | Pendiente |
