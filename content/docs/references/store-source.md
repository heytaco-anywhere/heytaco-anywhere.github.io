### HEYTACO_ANYWHERE_STORE_SOURCE

String value provides the source of store. Configures the database connection string. *The default value is the path of the embedded sqlite database file.*

```
HEYTACO_ANYWHERE_STORE_SOURCE=file:sqlite3.db?cache=shared&_fk=1
```

Example mysql connection string (below). See the [official driver](https://github.com/go-sql-driver/mysql#dsn-data-source-name) documentation for more connection string details.

```
HEYTACO_ANYWHERE_STORE_SOURCE=root:password@tcp(1.2.3.4:3306)/heytacoanywhere?parseTime=true
```

Example postgres connection string (below). See the [official driver](https://www.postgresql.org/docs/current/libpq-connect.html#LIBPQ-CONNSTRING) documentation for more connection string details.

```
HEYTACO_ANYWHERE_STORE_SOURCE=postgres://root:password@1.2.3.4:5432/postgres?sslmode=disable
```
