# HW 02

* Try to avoid code duplication. Especially, when you are working with ResultSet.
  Move retrieving data from ResultSet into Entity object to a separate private method.

* Remember that we can't do next operations on deleted manufacturers: get(), getAll(), update().

* Let's use TRUE/FALSE instead of 1/0 with `is_deleted` column in the sql queries.

* Don't make `manufacturers.name` UNIQUE.

* When creating a table in MySQL, use `bigint` column type for storing id.

* Use `if` or `while` with `resultSet.next()`. Don't do it without checking,
  because the result can be `null` and you will get a NPE after trying to get a value from `resultSet`.
  
* Use `PreparedStatement` over `Statement`, even for a static query with no parameters in `getAll()` method. It's the best practice, and it's slightly faster.

* Column naming:
    ```
    Wrong: manufacturers.manufacturerName, manufacturers.MANUFACTURER_NAME
    
    Good: manufacturers.name
    ```
* Don't use `Statement.RETURN_GENERATED_KEYS` only in `create` statement, it's not needed in other methods.

* Be attentive with:
    ```
        Wrong:
            String manufacturerName = restulSet.getString("name");
            Long manufacturerId = resultSet.getLong("id"); // return '0' if data is absent.
        Good:
            String manufacturerName = restulSet.getString("name");
            Long manufacturerId = resultSet.getObject("id", Long.class); // return 'null' if data is absent.
    ```

* Don't return `true` all the time in the method `delete`.
  Let's return boolean value depending on `preparedStatement.executeUpdate()` [result](https://docs.oracle.com/javase/7/docs/api/java/sql/Statement.html#executeUpdate(java.lang.String)).

  Example:
  ```
        ...
        int updatedRows = preparedStatement.executeUpdate();
        return updatedRows > 0;
  ```
  Better not use `updatedRows == 1`, `updatedRows >= 1` - the example above, that uses comparison with `0`, is more flexible.

* Let's save each query in a separate variable.
    ```
        Wrong:
            public List<Manufacturer> getAll() {
                try (Connection connection = ConnectionUtil.getConnection()
                    PreparedStatement preparedStatement = connection
                        .prepareStatement("SELECT * FROM manufacturers WHERE is_deleted = FALSE")) { // it's bad
                    ...
                } catch (SQLException ex) {
                    ...
                }
            }
            
        Good:
            public List<Manufacturer> getAll() {
                String query = "SELECT * FROM manufacturers WHERE is_deleted = FALSE"; // it's good
                try (Connection connection = ConnectionUtil.getConnection();
                    PreparedStatement preparedStatement = connection.prepareStatement(query)) {
                    ...
                } catch (SQLException ex) {
                    ...
                }
            }
    ```

* Best practices with closing Connections and/or PreparedStatements
    - You have to close the PreparedStatement after you're done with it and before you create a new one on the same connection.
    - Generally, when you close the connection it automatically closes the statement.
      But, for example, if for some reason you are using a connection pool (we are not using it now),
      and you call connection.close(), the connection will be returned to the pool,
      and the Statement will never be closed. Then you will run into many new problems!
      In any case, it's a good practice to always close and Statement explicitly and not to rely on Connection.close().
    - So let's close PreparedStatement as well as Connection (use try with resources for that).


* Use informative messages for exceptions.
    ```
        Wrong:
            throw new DataProcessingException("Can't get manufacturer", e);
            
        Good:
            throw new DataProcessingException("Can't get manufacturer by id " + id, e);
            throw new DataProcessingException("Can't insert manufacturer " + manufacturer, e);
    ``` 

* Don't use schema's name in your queries, cause you are configuring it while establishing a connection with DB.
```sql     
       Wrong:
        SELECT * FROM schemaname.manufacturers WHERE id = 1;                     
             
       Good:
        SELECT * FROM manufacturers WHERE id = 1;
```           
