### Common mistakes

* Don’t ignore checkstyle rules.
* Figure out which way is better to initialize your RegistrationServiceImpl class instance: `@BeforeEach` or `@BeforeAll`, what’s the difference?
* Make sure you name your methods according to [convention](https://google.github.io/styleguide/javaguide.html#s5.2.3-method-names).
* Add tests for all possible User's parameters (null login/password/age, user under 18/18/over 18 years old, negative age, and so on...).
* Make sure that after successful registration user was added to storage and `register` method returned correct user.
* Use `storageDao.add` instead of `register` method to add user for testing.
* Don't create one big if with all conditions. Better to split one big if into several small ones.

```java 
Bad example:

public User register(User user) {
 if (user.getLogin() != null 
   && user.getPassword() != null
   && user.getAge() < MIN_AGE) {
   throw new RuntimException("Invalid data");
 }
 return storageDao.add(user);
}
```

```java 
Good example:

public User register(User user) {
 if (user.getLogin() != null) {
   throw new RuntimException("Login can't be null");
 }
 if (user.getPassword() != null) {
   throw new RuntimeException("Password can't be null");
 }
 if (user.getAge() < MIN_AGE) {
   throw new RuntimeException("Not valid age");
 }
 return storageDao.add(user);
}
```

* You don’t need main method to see how your solution works, you have tests for this purpose.
* If you are expecting exception to be thrown in the test, you can do it this way:
```
assertThrows(ExpectedException.class, () -> object.methodUnderTest(inputParams);
```
* Don't use `NullPointerException`, because in such case we can't distinguish was this exception because of our mistake or because of validation.

* Move all hardcoded values to [constant fields](https://mate-academy.github.io/style-guides/java/java.html#s5.2.4-constant-names) and give them informative names.

* Check your code for coverage with tests, expected coverage should be 90%+. [How to run](https://www.jetbrains.com/help/idea/running-test-with-coverage.html#run-config-with-coverage)
