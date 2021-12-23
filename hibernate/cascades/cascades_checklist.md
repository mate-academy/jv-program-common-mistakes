# Common mistakes

* Think if you need to use JPA-specific or Hibernate-specific methods to make cascades work.
* Be consistent, don't use both `session.save()` and `session.persist()` in different daos. Choose single approach and use corresponding annotaions of Hibernate of JPA.
* In all of your dao classes you have `sessionFactory` object (which is passed via constructor). 
You should use it for the tests to pass. Use `HibernateUtil.getSessionFactory()`
ONLY if you want to run your solution in the main method.
* You don't need to create your own exception, let's throw `RuntimeException` in the catch block. 
* You need to open a transaction not only when creating entities but when removing as well.
* Don't just copy paste code from other dao (make sure your exception messages and variable names are correct for particular class.
* Don't forget about HQL coding conventions, all reserved words should be in lowercase