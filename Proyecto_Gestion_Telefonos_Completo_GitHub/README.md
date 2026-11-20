# Sistema de Gestión de Teléfonos Inteligentes | SQL Server

Proyecto académico de **Modelamiento de Bases de Datos**. Incluye modelo relacional en tercera forma normal (3FN), datos estructurados y un script de implementación para Microsoft SQL Server mediante **T-SQL**.

## Contenido

- [`gestion_telefonos.sql`](gestion_telefonos.sql): creación de base de datos, tablas, relaciones, carga de registros, índices, funciones, procedimiento almacenado, triggers y consultas de comprobación.
- [`docs/modelo_relacional_3FN.xlsx`](docs/modelo_relacional_3FN.xlsx): archivo original de modelamiento y datos organizados en diez hojas.

## Modelo relacional

| Hoja del Excel | Tabla SQL correspondiente | Filas de datos en Excel |
|---|---|---:|
| Marcas | `Marca` | 22 |
| Tiendas | `Tienda` | 8 |
| Sistemas_Operativos | `SistemaOperativo` | 233 |
| Hardware_Procesadores | `Procesador` | 159 |
| Pantallas | `Pantalla` | 377 |
| Baterias | `Bateria` | 102 |
| Multimedia_Video | `EspecificacionVideo` | 159 |
| Modelos_Telefono | `ModeloTelefono` | 469 |
| Variantes_Hardware | `ConfiguracionMemoria` | 705 |
| Precios_Inventario | `OfertaTienda` | 1708 |

El script SQL incluye una tabla adicional, `BitacoraOferta`, para registrar modificaciones de precios; por eso hay **10 hojas en Excel y 11 tablas SQL**. Los nombres de campos se adaptaron del Excel al esquema SQL.

## Elementos de T-SQL

- Claves primarias y foráneas para integridad referencial.
- 3 índices adicionales.
- 2 funciones, 1 procedimiento almacenado y 2 triggers.
- Carga de datos y consultas de verificación.

## Cómo ejecutar

1. Usa una instancia **de prueba** de Microsoft SQL Server.
2. Abre `gestion_telefonos.sql` en SQL Server Management Studio (SSMS).
3. Revisa el bloque inicial y ejecuta el script en un entorno donde puedas recrear la base.
4. Consulta las tablas y ejecuta las sentencias de comprobación al final del script.

> **Precaución:** el script comienza eliminando `BD_Gestion_Telefonos` si ya existe, lo que **borra su contenido**. No lo ejecutes en producción ni sobre datos que quieras conservar.

## Nota sobre el modelo

El Excel contiene las entidades y los datos originales; **no es una imagen de diagrama entidad-relación**. Para visualizar las relaciones gráficamente, se puede exportar un diagrama desde SSMS y añadirlo después en `docs/`.

## Alcance

Se revisaron los nombres y dimensiones de las hojas frente a las tablas definidas en el script. No se ha ejecutado el script contra una instancia SQL Server en esta revisión, por lo que no se certifica una validación de ejecución extremo a extremo.
