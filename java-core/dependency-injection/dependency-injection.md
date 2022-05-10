### Common mistakes

* Don't forget about informative variable names.
* You should use only `@Component` and `@Inject` annotations.
* Don't forget about annotations checks in your Injector class.
* Let's check instances map before new instance creation.
* Remember that we can replace multiple exceptions in the catch block with one common parent exception.
* When throwing an exception add an informative message to it. Also, don't forget to add an exception you're catching in `catch` block to the `RuntimeException` object you throw
``` 
Bad example: 
} catch(Exception e) {
  throw new SomeException("Can't initialize object with Injector");
}
```
``` 
Good example: 
} catch(Exception e) {
  throw new SomeException("Injection failed, missing @Component annotaion on the class " + someInfoAboutClass, e);
}
```
* It is better to replace many exceptions that have a common parent with a general parental exception.
``` 
Bad example: 
} catch (InvocationTargetException | InstantiationException
        | IllegalAccessException | NoSuchMethodException e) {
```
``` 
Good example: 
} catch (ReflectiveOperationException e) {
```
