### Common Mistakes

#### Explore Existing Methods of the `Character` Class
The `Character` class offers a variety of [methods](https://docs.oracle.com/en/java/javase/13/docs/api/java.base/java/lang/Character.html). You can use one of them to check if a character is a letter.

#### Prefer StringBuilder Over String or StringBuffer
Since the String object is immutable, each call for concatenation will result in a new String object being created. On the other hand, StringBuilder is mutable and is considered a very efficient way to concatenate strings. The compiler will replace concatenation with StringBuilder when we have a simple code row, but with loops, that won't work. [Java doc](https://docs.oracle.com/javase/7/docs/api/java/lang/String.html)

#### Pay Attention to Variable Naming
Incorrect naming can significantly impact your code readability!
```java
// Bad naming:
    char[] c;
    StringBuilder sb = new StringBuilder();
```  
```java
// Good naming:
    char[] lettersFromText;
    StringBuilder stringBuilder = new StringBuilder();
```  