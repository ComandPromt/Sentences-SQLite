# Sentences-SQLite

## Useful little scripts for SQLite

### Resumen de tipos numéricos en SQLite

| Tipo de dato | ¿Admite decimales? | Descripción                                   |
|--------------|---------------------|-----------------------------------------------|
| `INTEGER`    | ❌ No                | Enteros de hasta 8 bytes                      |
| `REAL`       | ✅ Sí               | Números de punto flotante (decimales)        |
| `NUMERIC`    | ✅ Sí               | Intenta usar entero o flotante, según el valor |
| `TEXT`       | —                   | Cadena de texto                               |
| `BLOB`       | —                   | Datos binarios                                |

### Format mydb.db

~~~sql
PRAGMA foreign_keys = OFF;

SELECT 'DROP TABLE IF EXISTS "' || name || '";'
FROM sqlite_master
WHERE type = 'table' AND name NOT LIKE 'sqlite_%';

PRAGMA foreign_keys = ON;

~~~
