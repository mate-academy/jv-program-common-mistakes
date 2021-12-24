# Common mistakes

* Let’s make the email unique.
* Custom `AuthenticationException` shouldn’t be `RuntimeException`.
* `findByEmail()` - don’t complicate with unnecessary variables, expect to receive only one String param 
  in method arguments.
* `findByEmail()` - should return Optional on both Dao and Service layers.
* Instead of `password.lenght() == 0` or `password.equals("")` use `isEmpty()` method of String class (if necessary).
* In `findByEmail()` method you can use `uniqueResultOptional()` method to retrieve User from Query.
* Create only one condition for throwing `AuthenticationException` in `login()` method. You may combine two checks: 
  whether the user has been found by login and does passwords match.
* Don’t forget to use `transaction.rollback()` in your dao implementations.
* Remember to add `catch` blocks for operations of all types on DAO layer.  
* Don’t use Dao in `authServiceImpl`.
* Run checkstyle and fix issues before push.
* You should create salt and hash password in UserService `add()` method.
