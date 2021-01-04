### DateTime API

#### Don't complicate if-else construction.
[Videso with example](https://www.youtube.com/watch?v=P-UmyrbGjwE&list=PL7FuXFaDeEX1smwnp-9ri8DBpgdo7Msu2)

#### If you create a formatter/use custom timezone, make it a constant field. Remember about informative names and `private` access modifiers.

#### Avoid magic numbers in your code.
They are should be constants.

#### Avoid calling LocalDate.now multiple times in one method. Let's create a variable in the method for this purpose.
LocalDate.now() gives us a different result if the next day has come. Of course, your code won't run for such a long time(I hope), but it's a good habit especially if you'll be working with LocalDateTime.now() method.

P.S. of course there are some cases when you need the strict current time in each point of your program even withing one execution, but this not one of those.

#### Before creating your own formatter, check out whether it is already defined in `DateTimeFormatter` class.
[Documentation](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/time/format/DateTimeFormatter.html)

#### Let's create a validator for tasks `parseDate()` and `customParseDate()`
Before start date-parsing, better check if the input string is correct. 
So let's create a class `DateValidator` with a method 
`isValid(String dateString, DateTimeFormatter dateFormatter)` that will return true/false.
[Read more](https://www.baeldung.com/java-string-valid-date).                                                                                
