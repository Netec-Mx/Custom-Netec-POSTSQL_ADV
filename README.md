<a href="https://netec.com">
  <img src="https://static.wixstatic.com/media/96edd2_934dddb3230b4b16b1d1c56c51143738~mv2.png" alt="Logo de Netec" width="300"/>
</a>

# PostgreSQL Avanzado [Custom Netec POSTSQL_ADV]

## Plataforma de laboratorios

Te damos la bienvenida a la **plataforma de laboratorios** del curso **PostgreSQL Avanzado**. Aquí aplicarás la administración, migración, recuperación, replicación, seguridad y optimización de PostgreSQL mediante un proyecto empresarial guiado. Los laboratorios siguen el caso de Distribuidora Andina y aprovechan los resultados de los capítulos anteriores.

## Lista de laboratorios

Cada uno de estos laboratorios está diseñado para ofrecerte una experiencia práctica. Haz clic en los enlaces para comenzar y sigue el orden de los capítulos.

## Capítulo 1. Introducción y Arquitectura de PostgreSQL

### [Práctica 1.1 Instalación de PostgreSQL en Linux](Capitulo01/README.md)

- **Descripción**: Instala PostgreSQL 16 en Linux, reconoce su arquitectura y utiliza el cliente `psql`. Crea la base `sales_pg`, el esquema comercial y las tablas de clientes, productos y pedidos; carga los datos iniciales y valida una transacción.
- ⏱️ **Duración estimada**: 100 min.

## Capítulo 2. Administración y Operación de PostgreSQL

### [Práctica 2.1 Administración y configuración de una instancia PostgreSQL](Capitulo02/README.md)

- **Descripción**: Configura la instancia y documenta su línea base de operación. Ajusta parámetros del servidor, controla el acceso mediante `pg_hba.conf` y verifica conexiones, sesiones, bloqueos y operaciones del clúster.
- ⏱️ **Duración estimada**: 100 min.

## Capítulo 3. Migración a PostgreSQL

### [Práctica 3.1 Migración de una base de datos a PostgreSQL](Capitulo03/README.md)

- **Descripción**: Migra un histórico de ventas desde SQL Server hacia PostgreSQL mediante extracción, transformación y carga en un esquema de transición. Concilia conteos, claves e importes antes de integrar los datos y definir el corte y la reversión.
- ⏱️ **Duración estimada**: 120 min.

## Capítulo 4. Respaldos y recuperación

### [Práctica 4.1 Implementación de estrategias de respaldo y recuperación](Capitulo04/README.md)

- **Descripción**: Genera y restaura respaldos lógicos, configura el archivado de WAL y obtiene una copia física. Comprueba la recuperación a un punto en el tiempo (PITR) en un clúster aislado y registra evidencias de recuperación.
- ⏱️ **Duración estimada**: 125 min.

## Capítulo 5. Replicación y alta disponibilidad

### [Práctica 5.1 Replicación asíncrona y síncrona](Capitulo05/README.md)

- **Descripción**: Configura una réplica física y comprueba el comportamiento de los modos asíncrono y síncrono ante una interrupción controlada. Complementa el ejercicio con una publicación y suscripción lógicas para distribuir tablas seleccionadas a una base de analítica.
- ⏱️ **Duración estimada**: 140 min.

## Capítulo 6. Seguridad

### [Práctica 6.1 Gestión de usuarios y autenticación, acceso remoto y permisos](Capitulo06/README.md)

- **Descripción**: Administra usuarios, roles y privilegios con acceso mínimo necesario. Configura autenticación SCRAM, conexiones TLS y políticas de seguridad por fila (RLS) para aislar datos por región, y verifica operaciones permitidas y rechazadas.
- ⏱️ **Duración estimada**: 100 min.

## Capítulo 7. Extensiones y Casos de Uso Especializados

### [Práctica 7.1 Implementación de una base de datos Geoespacial con PostGIS](Capitulo07/README.md)

- **Descripción**: Instala PostGIS e incorpora ubicaciones de clientes y de un centro de distribución. Ejecuta consultas de distancia, cobertura y proximidad con datos geoespaciales, y revisa el uso de índices GiST conservando las políticas de acceso regional.
- ⏱️ **Duración estimada**: 85 min.

## Capítulo 8. Actualización, estadísticas y monitoreo

### [Práctica 8.1 Actualización y optimización de PostgreSQL](Capitulo08/README.md)

- **Descripción**: Monitorea la actividad y analiza el rendimiento con estadísticas y planes de ejecución. Compara consultas antes y después de aplicar índices y mantenimiento, y ensaya una actualización de PostgreSQL 16 a 18 mediante dump/restore en un destino aislado.
- ⏱️ **Duración estimada**: 150 min.

---

## 📬 Contacto y más información

Si tienes alguna pregunta o necesitas más detalles, no dudes en [contactarnos](mailto:soporte@netec.com). También puedes encontrar más recursos en nuestra [página](https://netec.com).

---

¡Gracias por visitar nuestra plataforma! Revisa todos los laboratorios y comienza tu experiencia de aprendizaje.
