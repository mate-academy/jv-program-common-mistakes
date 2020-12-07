### Common mistakes

* Don’t ignore checkstyle rules.
* Figure out which way is better to initialize your Calculator class instance: `@Before` or `@BeforeClass`, what’s the difference?
* Make sure you name your methods according to [convention](https://google.github.io/styleguide/javaguide.html#s5.2.3-method-names).
* Add tests for each operation with different type of input params (positive values, negative values, zero etc) same goes for other operations.
* Check if you’ve added all unneeded files to .gitignore before pushing.
* You don’t need main method to see how your solution works, you have tests for this purpose.
* If you use `delta` for comparison - declare it as a constant.
* If you are expecting exception to be thrown in the test, you can do it this way:`@Test(expected = YourException.class)`.
* Try to avoid complex if else and switch case constructions that will make your code less flexible.
* Don’t return null when you receive an unexpected operator, it’s a bad practice. Let’s throw an exception.
* Check your code for coverage with tests, expected coverage should be 90%+. [How to run](https://www.jetbrains.com/help/idea/running-test-with-coverage.html#run-config-with-coverage)
