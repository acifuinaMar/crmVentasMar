# CRMVentas - Proyecto Final Base de Datos II

## Descripción

CRMVentas es un sistema de gestión comercial (CRM) desarrollado como proyecto final del curso Base de Datos II. El sistema permite administrar clientes, oportunidades de venta, actividades comerciales y el seguimiento del proceso de ventas mediante un tablero Kanban.

Además de las funcionalidades operativas, el proyecto incorpora técnicas avanzadas de administración de bases de datos como procedimientos almacenados, triggers, auditoría, optimización mediante índices, alta disponibilidad con Database Mirroring y un Data Warehouse alimentado mediante procesos ETL.

---

## Tecnologías Utilizadas

### Backend

* Node.js
* Express.js
* SQL Server 2019 / 2025

### Frontend

* HTML5
* CSS3
* JavaScript
* Bootstrap 5

### Base de Datos

* SQL Server Management Studio (SSMS)
* Stored Procedures
* Triggers
* Views
* Indexes
* Transactions
* Database Mirroring
* Data Warehouse
* ETL

---

## Funcionalidades Implementadas

### Gestión Comercial

* Administración de clientes
* Administración de oportunidades
* Administración de actividades
* Pipeline de ventas estilo Kanban
* Seguimiento del avance comercial

### Reportería

* Oportunidades por gestor
* Oportunidades por fecha
* Oportunidades ganadas y perdidas
* Dashboard analítico desde Data Warehouse

### Auditoría

* Registro automático de cambios
* Historial de movimientos de oportunidades
* Trazabilidad de operaciones críticas

---

## Programación en Base de Datos

### Funciones

* `fn_CalcularImportePonderado`

### Procedimientos Almacenados

* `sp_CambiarEtapaOportunidad`
* `sp_CerrarOportunidad`
* `sp_ETL_CargarDW_CRMVentas`

### Triggers

* `trg_ActualizarOportunidadPorEtapa`
* `trg_AuditarCambioEtapa`
* `trg_AuditarActualizacionOportunidad`

### Transacciones

Se implementaron transacciones explícitas utilizando:

```sql
BEGIN TRANSACTION
COMMIT TRANSACTION
ROLLBACK TRANSACTION
```

para garantizar la integridad de las operaciones críticas.

---

## Optimización

Se implementaron índices no agrupados para mejorar el rendimiento de:

* Consultas Kanban
* Reportes por vendedor
* Reportes por fecha
* Actividades comerciales
* Consultas de oportunidades activas

---

## Alta Disponibilidad

Se implementó Database Mirroring entre dos instancias:

### SQL1

Servidor Principal

### SQL2

Servidor Mirror

Características:

* Replicación síncrona
* Failover manual
* Recuperación ante fallos
* Continuidad operativa

---

## Data Warehouse

### Base Transaccional (OLTP)

```text
CRMVentas
```

### Base Analítica (OLAP)

```text
DW_CRMVentas
```

### Dimensiones

* DimCliente
* DimEmpleado
* DimFecha
* DimResultado

### Tabla de Hechos

* FactOportunidades

### ETL

El procedimiento:

```sql
sp_ETL_CargarDW_CRMVentas
```

extrae información desde CRMVentas, realiza transformaciones y carga los datos hacia el Data Warehouse.

---

## Estructura del Proyecto

```text
crmVentas/
│
├── public/
│   └── index.html
│
├── database/
│   ├── 01_funciones.sql
│   ├── 02_procedimientos_almacenados.sql
│   ├── 03_triggers_auditoria.sql
│   ├── 04_indices_optimizacion.sql
│   ├── 05_vistas_reportes.sql
│   ├── 06_datawarehouse_etl.sql
│   ├── 07_mirroring_alta_disponibilidad.sql
│   └── 08_pruebas_validacion.sql
│
├── server.js
├── package.json
└── README.md
```

---

## Instalación

### Clonar repositorio

```bash
git clone https://github.com/acifuinaMar/crmVentasMar.git
```

### Instalar dependencias

```bash
npm install
```

### Ejecutar aplicación

```bash
node server.js
```

### Abrir navegador

```text
http://localhost:3000
```

---

## Evidencias Implementadas

* CRUD completo
* Procedimientos almacenados
* Triggers
* Funciones
* Transacciones
* Auditoría
* Índices
* Vistas
* Reportes
* ETL
* Data Warehouse
* Database Mirroring
* Failover
* Dashboard Analítico

---

## Autor

**Maryori Acifuina**
**23 6640**

Proyecto Final – Base de Datos II - Sección B\
Universidad Mariano Gálvez de Guatemala\
2026
