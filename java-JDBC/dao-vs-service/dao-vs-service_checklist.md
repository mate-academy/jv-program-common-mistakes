# HW 03

* Make sure you are creating a new branch before start working. 
* Run __`mvn clean package`__ after finish homework and before sending the solution.
* Use wrapper for id: `Long id` but not `long id`. And remember what is the difference between `==` and `equals`.
* To display data while testing use Stream API `forEach()`, not `for` loop.
* Method `findFirst()` return Optional, so you should not use `Optional.ofNullable` anywhere.
* `find()` methods in Dao layer should return `Optional` (not in services). In the service layer better call method `get()` on Optional and return the object.
* You should not have any additional logic on Dao layer except managing database operations. All business logic must be on service layer.
