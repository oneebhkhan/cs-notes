### Introduction

JDBC => Java Database Connection


API that establishes connection between a database and a Java application that intends to use that database.

### Datatypes in Java <=> SQL

### Architecture

Application => JDBC API => JDBC Managers => JDBC Drivers => Database

### Requirements:
1. Latest JDK

### Steps to Connect JDBC
1. Import Packages (What packages?)
2. Load and register your driver (e.g. MySQL Driver)
3. Connect database
4. Write Query
5. Execute Query (executeQuery)
6. Process results
7. Closing statement
8. Closing connection