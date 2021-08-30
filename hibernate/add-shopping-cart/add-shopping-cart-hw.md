# Common mistakes

1. Check the correct relation in MovieSession entity. 
1. Model `Ticket` has relationships with `MovieSession` and `User` entities. 
    Be careful choosing the type of these relationships. 
    __Remember__ that one user can buy many tickets, and many users can attend one movie session.
1. Don't cast result of `query.getSingleResult()` or `query.uniqueResult()`, it works just fine without it:
```
    Wrong:
       return (ShoppingCart) query.getSingleResult();
    
    Good:
       return query.getSingleResult();
```
1. Use `@MapsId` with `ShoppingCart`. Think about whether to use an annotation `@GeneratedValue` in `ShoppingCart`.
1. For saving ShoppingCart use `save()` method instead of `persist()`. 
The reason is that `ShoppingCart` object will have the `transient` state before the session opened, but its `User` object will be `detached`. 
`persist()` method throws `PersistenceException` if working with detached entities, when `save()` returns it to managed state.
1. Use method `registerNewShoppingCart()` in `AuthenticationServiceImpl` class in `register()` method.
1. Try to think what should be called first `userService.add(user)` or `registerNewShoppingCart()`.
1. Try to think what should you do first in method `addSession`: 
`ticketDao.add(ticket);` or `shoppingCartService.update()`
