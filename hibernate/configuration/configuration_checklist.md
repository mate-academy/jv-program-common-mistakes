# Common mistakes

* You should have only `Movie` model with dao and service layer. Don't create other models and don't push them to PR. 
* If you create SessionFactory seesionFactory as local variable and it repeats in code move it to the class variable.
* You don’t need to set id for your entity explicitly. It'll be done by Hibernate.
* Don’t add dependencies that you don't use to `pom.xml`.
* Don't add alfa version of dependencies, they might work unpredictable and cause problems.
* Use try with finally, where you use transaction and try with resources with Read operations.
* Add a private default constructor to `HibernateUtil` class in order to prevent creating `HibernateUtil` objects.
* Don’t create a default constructor when it is not needed.
* Do not push redundant files or folders (iml, .idea, target, etc).
