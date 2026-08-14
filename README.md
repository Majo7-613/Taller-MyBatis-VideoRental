# Taller de Persistencia con MyBatis - VideoRental

## Tecnologías y Herramientas

* **Lenguaje:** Java (JDK 8+)
* **Framework de Persistencia:** Apache MyBatis
* **Base de Datos:** SQLite JDBC (`bd.sqlite3`)
* **Gestor de Dependencias:** Apache Maven

## Características e Implementaciones

### Parte I: Configuración y Mapeos Complejos
* **Type Aliases:** Definición de alias cortos para las entidades del dominio (`Cliente`, `Item`, `ItemRentado`, `TipoItem`) en `mybatis-config.xml`.
* **Mapeo Grafo de Objetos:** Reconstrucción de un `Cliente` junto con su colección de `ItemsRentados`, sus `Items` asociados y `TipoItem` usando una única consulta SQL con `LEFT JOIN`.
* **Prefijos de Columnas:** Resolución de ambigüedades entre columnas con nombres colisionados (`id`, `nombre`, `descripcion`) mediante `columnPrefix` en los `resultMap`.

### Parte II: Consultas Parametrizadas y Refactorización
* **Anotaciones `@Param`:** Integración de parámetros explícitos en las interfaces de mapeo Java (`ClienteMapper` e `ItemMapper`).
* **Inyección de Parámetros:** Consultas filtradas por parámetros (`consultarCliente`, `consultarItem`) y operaciones de inserción (`agregarItemRentadoACliente`, `insertarItem`).
* **Reutilización de Mapeos (DRY):** Centralización de `ItemResult` dentro de `ItemMapper.xml` y referenciación mediante el espacio de nombres absoluto desde `ClienteMapper.xml`.


## Ejecución del Proyecto

Para compilar y ejecutar el programa de prueba `MyBatisExample`:

```bash
mvn compile exec:java "-Dexec.mainClass=edu.unisabana.dyas.samples.services.client.MyBatisExample"
