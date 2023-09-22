### DateTime API

#### Simplify If-Else Constructions [Detailed explanation](./../complicated-if-else.md)

#### Make Formatters/Custom Timezones Constant Fields
If you create a formatter or use a custom timezone, make it a constant field. Remember to use informative names and `private` access modifiers.

#### Avoid Magic Numbers in Your Code
These should be defined as constants.

#### Avoid Multiple Calls to LocalDate.now in a Single Method
Create a variable within the method for this purpose. `LocalDate.now()` yields a different result if the date changes to the next day during execution. While your code may not run for such a long duration (hopefully), it's a good habit to adopt, especially when working with the `LocalDateTime.now()` method.

P.S. Of course, there are cases when you need the exact current time at each point in your program within a single execution, but this is not one of those cases.

#### Check Existing Formatters Before Creating Your Own
Before creating your own formatter, check whether it's already defined in the `DateTimeFormatter` class. [Documentation](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/time/format/DateTimeFormatter.html)