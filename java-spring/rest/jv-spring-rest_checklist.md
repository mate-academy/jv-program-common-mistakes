# Spring REST

* Return `id` of entity in all response DTOs.
* Remember about [REST resource-naming convention](https://restfulapi.net/resource-naming/).
* In your mappers prefer setters over big constructors while converting entity to dto and vice versa.
* Use Stream API while working with lists in your mappers.
* If on dao layer you keep common logic in class AbstractDaoImpl it should be abstract. Check then how to put
  [annotations](https://www.baeldung.com/spring-autowired-abstract-class#constructor-injection) in case of abstract class.
