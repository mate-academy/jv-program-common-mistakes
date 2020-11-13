### Common mistakes

#### Divide program logic
Large methods is very difficult to read and understand. So methods should be short, between 5-15 lines.
And you should remember that one method should be responsible for one task.

For example: "write to file" or "create report" - is a separate operations. So we should create separate methods for them.

#### Method naming convention
Correct [method names](https://mate-academy.github.io/style-guides/java/java.html#s5.2.3-method-names) is first step to pure code.

#### Remember about informative name of the variables

#### Using StringBuilder instead of String to concat data
Keep in mind that String concatenation creates many new objects that take up a lot of memory.

#### Constants
If you have strange strings or numbers in the code it's better to declare them as constants.
The name of the constant should display this object's purpose.

#### Using public access modifiers everywhere
If method has only util purpose and is used only inside the same class it should not be 
`public`. Keep your code as closed as possible in order to follow encapsulation principal.

#### Don't ignore exceptions
Leaving empty catch block or `e.printStackTrace` here is a bad practice. 
Better re-throw `RuntimeException` with original exception and some message in the parameters:
```
catch (Exception e) {
    throw new RuntimeException("Can't read data from the file " + fileName, e);
}
```
