### Common mistakes

* Don’t ignore checkstyle rules.
* Figure out which way is better to initialize your RegistrationServiceImpl class instance: `@BeforeEach` or `@BeforeAll`, what’s the difference?
* Make sure you name your methods according to [convention](https://google.github.io/styleguide/javaguide.html#s5.2.3-method-names).
* Add tests for all possible User's parameters (null login/password/age, user under 18/18/over 18 years old, negative age, and so on...)
* You don’t need main method to see how your solution works, you have tests for this purpose.
* If you are expecting exception to be thrown in the test, you can do it this way:
```
assertThrows(ExpectedException.class, () -> object.methodUnderTest(inputParams);
```

* Check your code for coverage with tests, expected coverage should be 90%+. [How to run](https://www.jetbrains.com/help/idea/running-test-with-coverage.html#run-config-with-coverage)
