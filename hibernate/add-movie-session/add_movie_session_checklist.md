# Common mistakes

* Don’t add dependencies that you don't use to `pom.xml`.
* Do not create redundant functionality, like methods that are not required by the task.
* Don’t just copy paste code from other dao (make sure your exception messages and variable names are correct for a particular class).
* Don’t get all `MovieSession` from dao and then sort them on service layer in `findAvailableSessions()`. 
It’s better for performance to extract "ready to use" data from DB on dao layer.
* Movie sessions from `findAvailableSessions()` should have running time limited within the day that your receive as input parameter: `LocalDate date`.
* Let's return `Optional` in `get()` method on dao layer, and the entity on service layer.
* Think what the difference between `getSingleResult()`, `uniqueResult()` and `uniqueResultOptional()`? Which one should we use?
* Don’t create a default constructor when it is not needed.
* Do not push redundant files or folders (iml, .idea, target, etc).
* Run checkstyle and fix issues before push.
