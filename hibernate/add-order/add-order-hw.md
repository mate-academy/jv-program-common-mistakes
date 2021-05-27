# Common mistakes 

1. Get information about order and tickets that were purchased in the method `getOrdersHistory`.
You can use inner join or a separate query for this purpose. `FetchType.EAGER` is a bad practice. 
See more [here](https://thorben-janssen.com/common-hibernate-mistakes-cripple-performance/#Mistake_1_Use_Eager_Fetching)
 
1. Don't create method `completeOrder(ShoppingCart shoppingCart)` on the dao layer. 
Let's create `add(Order order)` instead. 

1. Check carefully the relationships in `Order` class. You should use `OneToMany` with `tickets`.

1. When passing tickets from shoppingCart to order — pass the copy of this list(you can use `ArrayList` constructor for this);
The reason is that Hibernate will automatically delete these tickets from shoppingCart(in DB) after noticing them in our order object. 
Let's do this manually using `clear()` method from `ShoppingCartService` after the order with tickets has been created.

1. Run checkstyle and fix issues before push (also setup Travis CI if you haven't done it before).
