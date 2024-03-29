## Common mistakes (jv-web-security)

* Remove autogenerated comments from `index.jsp`.
* Don't begin class or method implementation with empty line. Remove all redundant empty lines, be careful :)
* Do not add `password` in driver `toString()` method implementation and do not show it in the JSP.
* In AuthenticationFilter, think if this check `driverService.get(userId) == null` will actually work.  
If inside your `driverService.get()` you are currently calling `get()` on Optional, 
you can omit this check in AuthenticationFilter.
* Both in AuthenticationServiceImpl and in AuthenticationFilter, try to use only one `if` block.
* If you use `sendRedirect()` method in your controllers, please pass `request.getContextPath() + "/your-endpoint"` as a parameter.
Currently, the context path is empty, but if it is not, your code still should work.
* Keep your endpoints naming consistent. For example, `GetMyCurrentCarsController` should have endpoint like this: `/drivers/cars`
* In the `AuthenticationFilter` class, better create a `Set<String>` with allowed urls (you can initialize it in the `init()` method). 
  Then in the method `doFilter()` do following check:
    ```
      if (allowedUrls.contains(url)) {
            ...
      }
    ```
* Let's inject `driverService` into AuthenticationServiceImpl class using `@Inject` annotation.
* Remember about `this()` when you create a lot of constructors:
    - Bad practice:
        ```java
            public class User {
                private String name;
                private int age;
                private String email;
                private String password;
                
                public User(String name, int age, String email) {
                    this.name = name;
                    this.age = age;
                    this.email = email;
                }
                
                public User(String name, int age, String email, String password) {
                    this.name = name;
                    this.age = age;
                    this.email = email;
                    this.password = password;
                }
            }
        ``` 
    - Good practice: 
        ```java
            public class User {
                private String name;
                private int age;
                private String email;
                private String password;
                
                public User(String name, int age, String email) {
                    this.name = name;
                    this.age = age;
                    this.email = email;
                }
                
                public User(String name, int age, String email, String password) {
                    this(name, age, email);
                    this.password = password;
                }
            }
        ```
