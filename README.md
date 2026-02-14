# hairball ☕

JDBC driver for SQL Server. Were sorry. Java made us do this.

Part of [CopyCat](https://github.com/copycatdb) 🐱

## What is this?

A JDBC Type 4 driver for SQL Server. Uses [tabby](https://github.com/copycatdb/tabby) via JNI because apparently we hate ourselves.

```java
Connection conn = DriverManager.getConnection(
    "jdbc:copycatdb://localhost:1433;databaseName=mydb",
    "sa", "password"
);

PreparedStatement stmt = conn.prepareStatement("SELECT * FROM users WHERE id = ?");
stmt.setInt(1, 42);
ResultSet rs = stmt.executeQuery();
while (rs.next()) {
    System.out.println(rs.getString("name"));
}
```

## Why?

Because the mssql-jdbc driver has been carrying the weight of backward compatibility since the early 2000s and deserves a vacation. We are the younger, slightly irresponsible replacement that shows up with a Rust backend and a bad attitude.

## The Name

Were calling it hairball because:
1. Java projects always produce something you need to cough up
2. JAR files are just hairballs of compressed classes
3. We tried to name it something dignified but Java wouldnt let us

## Status

🚧 Coming eventually. Were still reading the JDBC spec. Its 400 pages. Send help.

## Attribution

Inspired by [pgjdbc](https://github.com/pgjdbc/pgjdbc) and [mssql-jdbc](https://github.com/microsoft/mssql-jdbc). Both are monuments to human endurance.

## License

MIT
