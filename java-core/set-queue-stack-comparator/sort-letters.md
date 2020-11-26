### Common mistakes

#### Ignoring existing methods of the `Character` class
Class `Characters` has a lot of [methods](https://docs.oracle.com/en/java/javase/13/docs/api/java.base/java/lang/Character.html). 
You can use one of them to check if a character is a letter.

#### Use String or StringBuffer instead of StringBuilder.
Since the String object is immutable, each call for concatenation will result in a new String object being created.
On the other hand, StringBuilder is mutable and thus is considered to be a very efficient way to concatenate Strings.

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
