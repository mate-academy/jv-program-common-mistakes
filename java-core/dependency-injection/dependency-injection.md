### Common mistakes

* Don't forget about informative variable names.
* You should use only `@Component` and `@Inject` annotations.
* Don't forget about annotations checks in your Injector class.
* Let's check instances map before new instance creation.
* Remember that we can replace multiple exceptions in the catch block with one common parent exception.
* When throwing an exception add an informative message to it
``` 
Bad example: 
  throw new SomeException("Can't initialize object with Injector");
```
``` 
Good example: 
  throw new SomeException("Injection failed, missing @Component annotaion on the class " + someInfoAboutClass);
```
