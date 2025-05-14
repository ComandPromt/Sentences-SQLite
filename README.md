# Sentences-SQLite

## Useful little scripts for SQLite

### Format mydb.db

~~~sql
PRAGMA foreign_keys = OFF;

SELECT 'DROP TABLE IF EXISTS "' || name || '";'
FROM sqlite_master
WHERE type = 'table' AND name NOT LIKE 'sqlite_%';

PRAGMA foreign_keys = ON;
~~~
