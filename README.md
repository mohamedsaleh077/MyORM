# MyORM
a simple php class to build the query and run it based on another class to connect to database nased on Eloqount

I used https://github.com/Wagner-Souza/eloquent-orm/blob/main/orm/Database.php as a reference

## How to use?
1. you need Database Class with it
2. you will build query using the chain potatos
ex:
```
select(..)->insert(...)->build()->selectAll(...)->build()->execute();
```
you can use one select, insert, delete, update before every build, if you used two selects, it will be overridden
select, selectAll, count, all of them are select
`build()` to save your query.

## What params would you love?
selectAll( tablename )
count( tablename, column = *)
select( TableName , [col1, col2, col3], alias = "")

join( tablename , PKcolumn, FKcolumn, "left" "right" "inner" "")
```
where([
         [column, "=", "or"], [column, "!=", "and"], [column, "like"],
         [
             [column, "=", "and"],
             [column, "LIKE"]
         ] for grouping
         , [column, "="] ]);
```
order(column, $type = "a for ASC and d for DESC, a is default")

insert(tablename, array of columns) the function will make columnname VALUES :columnname

update(tablename, columns) must have where()
delete(table name) must have where()

update and delete without where() will never run
