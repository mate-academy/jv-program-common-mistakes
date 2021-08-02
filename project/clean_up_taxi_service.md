# Taxi service cleanup

1. You must [create a new repo](add_video_about_it) with project collected from tasks from JDBC and Web modules.
1. Remove `Main` class.
1. Add README with project description.
1. If your code repeats several times inside of a class, move it to separate method.
1. Check your method signatures and remove `throws Exception` if your code cannot throw this exception.
1. Do not ignore Intellij Idea hints, read and fix them where applicable.
1. Go over your whole project, if you have variables/methods/fields that are never used don’t forget to remove them.
1. Check all url-mapping in project.
1. Add logger to your project: 
    - you can log some information in the AuthenticationService about correct or incorrect login.
    - relative path to `.log` file can not work, so use absolute path instead and add notes about it in the `README.md` file. 
1. Remove from project commented code, sout, `e.printStackTrace()` or replace them with logger.
1. Don't push `log` folder, `target`, `.iml` to GitHub (add them to `.gitignore` before committing any code).
