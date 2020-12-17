__date-time-api__
* Don't complicate if-else construction: [example](https://www.youtube.com/watch?v=P-UmyrbGjwE&list=PL7FuXFaDeEX1smwnp-9ri8DBpgdo7Msu2)
* If you create a formatter/use custom timezone, make it a constant field. Remember about informative names and `private` access modifiers.
* Avoid magic numbers in your code.
* Avoid calling LocalDate.now multiple times in one method. Let's create a variable for this purpose.
* Before creating your own formatter, check out whether it is already defined in `DateTimeFormatter` class.
* We can catch two particular exceptions in the same catch block, 
but in case of any trouble we should be able to identify them - for now you can use System.out.println().
