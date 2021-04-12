# Git commit messages

General recommmendation - let's write meaningful commit messages.

Imagine that you read your code in two months. I bet you won't understand exactly what you did in your committee. 
Or, imagine how "convenient" it would be to read code in which there is more than 100k commits. 
For example, in the [TensorFlow framework](https://github.com/tensorflow/tensorflow/commits/master) from Google (designed for ML and contains more than 2 million lines of code)

Bad naming examples
```
  - v 1.1.1; 
  - done;
  - first solution;
  - second solution;
  - finally solution;
  - now it's really finally solution #32 
```

Good naming examples
```
  - added Builder pattern implementation
  - fixed NPE in UserService
  - updated REAMDE.md
```

Read more:
- https://chris.beams.io/posts/git-commit/
