### Common mistakes

#### Check existing methods of the `Character` class
Class `Characters` has a lot of [methods](https://docs.oracle.com/en/java/javase/13/docs/api/java.base/java/lang/Character.html). 
You can use one of them to check if a character is a letter.

#### Use StringBuilder instead of String or StringBuffer.
Since the String object is immutable, each call for concatenation will result in a new String object being created.
On the other hand, StringBuilder is mutable and thus is considered to be a very efficient way to concatenate Strings.
Compiler will replace concat with StringBuilder when we have simple code row but with a loops that won't work. [java doc](https://docs.oracle.com/javase/7/docs/api/java/lang/String.html)

#### Variable naming
Incorrect naming may have significant impact on your code readability!  
```
Bad naming:
    char[] c;
    StringBuilder sb = new StringBuilder();
```  
```
Good naming: 
    char[] lettersFromText;
    StringBuilder stringBuilder = new StringBuilder();
```  
