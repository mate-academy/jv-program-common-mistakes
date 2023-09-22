### Common Mistakes

#### Don't Ignore Exceptions
Leaving an empty catch block or using `e.printStackTrace` is a bad practice. It's better to re-throw a `RuntimeException` with the original exception and include a message in the parameters:
```java
catch (Exception e) {
    throw new RuntimeException("Can't write data to file " + fileName, e);
}
```

#### Use Informative Variable Names
Ensure that the names of your variables are informative and reflect the data they hold. This makes your code more readable and understandable to others, and to "future you."