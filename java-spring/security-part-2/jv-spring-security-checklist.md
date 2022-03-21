# Spring security part 2

1. Be attentive with user-role relationship. One user can have a lot of roles and also one role can be attached to a lot of users.
2. Don’t create a new role every time you add user, attach one, that you already have in db.
3. Add `USER` role to user at `Authentication` service in the method `register()`.
4. Better use `Set` of roles in the user model, instead of the `List` (don't forget about equals and hashcode).
5. Don't use `left join` with user and roles on the dao layer. It is impossible to get user without role. Better use `inner join`.
6. In UserDetailsService let's throw specific Spring exception - `UsernameNotFoundException` when user is not found by username.
7. Don’t create beans using “new”, we have Autowiring for this purpose.
8. Don’t hash password twice while adding user to db (for example on AuthService and then on UserService).
9. Be careful when you check user for null in CustomUserDetailsService, can user be null, when we get him using `Optional.get()` or `Optional.orElseThrow()`?
10. Use annotation `@Enumerated(value = EnumType.STRING)` for `roleName` field, in order for it
    to be displayed and stored properly in db.
11. Be careful in `getByName()` method on dao layer! You should pass enum to query (not String), 
    otherwise you won't be able to get Role by name.
12. If you use `@PostConstruct` and data is injected twice, check this class isn't present twice under
    `@ComponentScan` annotation at the same time(for example in WebConfig and AppConfig).
13. When you create `UserBuilder`, move package name from method to imports.
14. You don't need to encode password in UserDetailsService.
15. Don't use annotation `@Controller` above DataInitializer class, because we don't have endpoints here, so it isn't controller.
