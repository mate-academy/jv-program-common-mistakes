#Spring Security

1. Be careful with CustomGlobalExceptionHandler. Let's use `getAllErrors()` instead of `getFieldErrors()`.
1. Don't forget to add `SecurityConfig.class` in `MyWebAppInitializer` -> `getRootConfigClasses()`.
1. Be careful with `@Target` annotation. Choose correct [ElementType](https://docs.oracle.com/javase/8/docs/api/java/lang/annotation/ElementType.html).
1. Add your custom email validation annotation above a field and password annotation above the class.
1. Remember about parameterizing interface ConstraintValidator with two parameters.
1. Don't override method initialize(), we don't need it in validator class.
1. Don't forget to rename parameters in isValid() method.
1. Let's create a constant with regex to check email. Remember about [naming](https://mate-academy.github.io/style-guides/java/java.html#s5.2.4-constant-names).
1. Remember, that `null.equals(smth)` == NPE. HINT: be careful with implementation of the `isValid()` method.
1. Don't repeat checks for fields: you must ensure `email` field not to be null in your custom Validator, so there is no need to put `@NotNull` for that field as well in Dto class.
1. Can we use `@NotNull` annotation above the field with primitive data types? Be careful to use only the suitable annotations :)
1. Use `@Autowired` with `PasswordEncoder` in `UserServiceImpl`.
1. Don't change `findByEmail()` method in UserController - this method is supposed to return info about any user.
1. Be sure you have the `@Valid` annotation in your controllers for the validation to take effect.
1. Your custom constraints should have the obligatory parameters: `group()` and `payload()`.
1. For validation use classes from `javax.validation` package.
