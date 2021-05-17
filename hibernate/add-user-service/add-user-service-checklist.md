# Common mistakes

* Let’s make the login unique.
* Custom `AuthenticationException` shouldn’t be `RuntimeException`.
* `findByEmail()` - don’t complicate with unnecessary variables, expect to receive only one String param 
  in method arguments.
* `findByEmail()` - should return Optional on Dao layer.
* In `findByEmail()` method you can use `uniqueResultOptional()` method to retrieve User from Query.
* Create only one condition for throwing `AuthenticationException` in `login()` method. You may combine two checks: 
  whether the user has been found by login and does passwords match.
* Don’t forget to use `transaction.rollback()` in your dao implementations.
* Don’t use Dao in `authServiceImpl`.
* Loggers should be informative (if they are present).
* Run checkstyle and fix issues before push.
* You should create salt and hash password in UserService `add()` method.
