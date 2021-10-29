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

#### Don't create temporary variables if you can directly return value from the method
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
```
Bad example:

public class UserService {
    public static User findByEmail(String email) {
       //some implementation
    }
}

public class Main {
    public static void main(String[] args) {
        User user = UserService.findByEmail("email@gmail.com");
    }
}
```
```
Improved example:

public class UserService {
    public User findByEmail(String email) {
       //some implementation
    }
}

public class Main {
    public static void main(String[] args) {
        UserService userService = new UserService();
        User user = userService.findByEmail("email@gmail.com");
    }
}
```


#### Don't create several instances of the same class if you can use only one instance for your purposes
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

#### Pay attention to access modifiers

Classes, fields, constructors, methods must have access modifiers otherwise default will be used that isn't a good practice.

#### Use for loop for creating several objects of the same class 
For example, you need to create several users and write them in an array. In our case let's say number of users is 3.
```
Bad example:

public class Main {
    public static void main(String[] args) {
        User[] users = new User[3];
        User firstUser = new User();
        User secondUser = new User();
        User thirdUser = new User();
        users[0] = firstUser;
        users[1] = secondUser;
        users[2] = thirdUser;
    }
}
```
```
Improved example:

public class Main {
    public static void main(String[] args) {
        User[] users = new User[3];
        for(int i = 0; i < users.length; i++) {
            users[i] = new User();
        }
    }
}
```

#### Write informative messages when you commit code or open a PR.
         
Bad example of commit/PR message: `done`/`fixed`/`commit`/`solution`/`added homework`/`my solution` and other one-word, abstract or random messages. 
