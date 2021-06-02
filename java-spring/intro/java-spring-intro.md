# Spring Intro

1. Whenever you perform operations with the DB, don't forget about transaction and to close connection after you're done.
2. Do we need HibernateUtil after the task is completed?
3. Keep your code clean (don't push commented code, remember about empty lines in the end of the file).
4. Don't add dependencies, that you don't currently use, it's a bad practice.
5. Use `try-finally` when you work with transaction and `try-with-resources` with read operations.
6. Make sure you've added all unneeded files to .gitignore before you push your code.
7. Check if you've put correct access modifiers everywhere.
8. What is better: setter, constructor, or field injection? Think why.
9. Use informative variable names.
