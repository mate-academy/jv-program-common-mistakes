### Common mistakes

#### Please don't add redundant empty lines to your code.
We don't need them after class declaration or method signature.
```
Bad example:

public class Main {

    public static void main(String[] args) {
    
        System.out.println("Hello world!");
    }
}
```
```
Improved example:

public class Main {
    public static void main(String[] args) {
        System.out.println("Hello world!");
    }
}
```

#### Don't create several instances of the same class if you can use only one instance for your purposes
```
Bad example:

public User createUser(String name, int age) {
    User user = new User(name, age);
    return user;
}
```
```
Improved example:

public User createUser(String name, int age) {
    return new User(name, age);
}
```

#### Don't use static methods in your solution
Static methods are in general a bad practice. Let’s better create an instance of a class which method you want to call

#### Don't create reference variable if you can return object without it
```
Bad example:

public class Main {
    public static void main(String[] args) {
        String[] emails = {"myEmail@gmail.com", "not@Valid@.g.com"};
        for(String email : emails) {
            if (new EmailValidator().isValid(email)) {
                System.out.println("Email " + email + " is valid");
            }
        }
    }
}
```
```
Improved example:

public class Main {
    public static void main(String[] args) {
        String[] emails = {"myEmail@gmail.com", "not@Valid@.g.com"};
        EmailValidator emailValidator = new EmailValidator();
        for(String email : emails) {
            if (emailValidator.isValid(email)) {
                System.out.println("Email " + email + " is valid");
            }
        }
    }
}
```

#### Don't forget how to name constants according to style guide (the same with naming of enum values)

https://mate-academy.github.io/style-guides/java/java.html#s5.2.4-constant-names

#### Write informative messages when you commit code or open a PR.
         
Bad example of commit/PR message: `done`/`fixed`/`commit`/`solution`/`added homework`/`my solution` and other one-word, abstract or random messages. 
