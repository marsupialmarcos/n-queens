# n-queens
This is a project I completed as a student at [hackreactor](http://hackreactor.com). This project was worked on with a pair.

# SPRINT SIX: N-Queens

**The problem in a nutshell**

Given an n x n chessboard, how many different ways can you place n queens, such that none of them are attacking each other?

**For your consideration**

Pondering the following questions (in order) will help you conceptualize a solution:

* Given an n x n chessboard, how would you place n rooks such that none of them are attacking each other?
* Given an n x n chessboard, how many different ways can you place n rooks, such that none of them are attacking each other?
* Given an n x n chessboard, how would you place n queens such that none of them are attacking each other?
* Given an n x n chessboard, how many different ways can you place n queens, such that none of them are attacking each other?

You'll run into some questions like this (but easier) during some interviews, and during your day-to-day work. This repo is a playground for thinking about this kind of problem.

**Helpful Groundwork**

To get started, we've provided a visualizer for your algorithms. Most algorithm questions are posed abstractly, but this Backbone app will help you see what's going on inside your code more easily.

To make use of it, open BoardViewer.html. You'll be implementing the conflict detection functions in src/Board.js as stepping stones to your solution.

**Install Pomander**

In Terminal, run the following command from within this repository:
```javascript
curl -s https://raw.githubusercontent.com/reactorcore/pomander/master/bin/install | bash
```
Pomander will check your code for syntax errors and violations against the Hack Reactor style guide before each commit.


It uses a pre-commit hook to run staged files through eslint before each commit. eslint is a linter that will block your commit should you have any syntax errors, or, should you violate the Hack Reactor style guide. There are some preferred whitespace style rules that will give warnings but not block your commit. Your work will be of a higher quality if you follow the instructions of the linter. That said, if the linter gives you any funny bugs, these bugs are not intentional, and you should feel free to skip using it during commits with the --no-verify option.

# Bare Minimum Requirements
*(Read this section and the Helpful Info section before beginning. After completing the bare minimum requirements, proceed to the Advanced content section.)*

Some of the helper functions in src/Board.js have been completed for you, and some have not. You should only need to edit the functions listed below.

* Open *src/Board.js* and fix the incomplete helpers (look for the 'start here' section) such that the specs in *spec/BoardSpec.js* pass. To see if your specs are passing, open *SpecRunnner.html* and look at the 'Board' section. Doing so will help you understand the problem more thoroughly, and will make the visualizer show any conflicts on the board.
  * **hasRowConflictAt():** test if a specific row on this board contains a conflict
  * **hasAnyRowConflicts():** test if any rows on this board contain a conflict
  * **hasColConflictAt():** test if a specific column on this board contains a conflict
  * **hasAnyColConflicts():** test if any columns on this board contain a conflict
  * **hasMajorDiagonalConflictAt():** test if a specific major diagonal on this board contains a conflict
  * **hasAnyMajorDiagonalConflicts():** test if any major diagonals on this board contain a conflict
  * **hasMinorDiagonalConflictAt():** test if a specific minor diagonal on this board contains a conflict
  * **hasAnyMinorDiagonalConflicts():** test if any minor diagonals on this board contain a conflict
* Fill in the functions in *src/solvers.js.* Fill them out so they accomplish the stated goals and pass the tests in *spec/solversSpec.js*
  * **findNRooksSolution():** returns a single solution to the n-rooks problem
  * **8countNRooksSolutions():** returns a count of the total number of solutions to the n-rooks problem
  * **findNQueensSolution():** returns a single solution to the n-queens problem
  * **countNQueensSolutions():** returns a count of the total number of solutions to the n-queens problem
* Identify the time complexity of each of your helper methods, as well as for each of your working solutions

**Helpful Info**
* Don't reinvent wheel where you don't have to. Use the Board constructor you build out in *src/Board.js* in your code. You can also access it within the Chrome console easily after opening *BoardViewer.html*
* Create new board instances that have access to all the helper methods you write in src/Board.js
  * *example: var board = new Board({n:5})*
* Rather than setting or getting object properties directly with plain JavaScript, Backbone provides the get and set methods. Play with the getters and setters that Backbone provides
  * *example: board.get(3)* will return the 3rd row of the instance board (assuming that instance exists)
* **Rows:** run horizontally, left to right
* **Columns:** run vertically, top to bottom
* **Major:** Diagonals run diagonally, top-left to bottom-right
* **Minor:** Diagonals run diagonally, top-right to bottom-left

In chess the rook piece moves and attacks horizontally (along rows) or vertically (along columns), through any number of unoccupied squares
In chess the queen piece moves and attacks horizontally (along rows), vertically (along columns), or diagonally (along major and minor diagonals), through any number of unoccupied squares

# ADVANCED CONTENT
Our advanced content is intended to throw you in over your head, requiring you to solve problems with very little support or oversight, much like you would as a mid or senior level engineer.
* Optimize the time and/or space complexity of your solvers. Here are some ideas:
  * Consider the memory usage of your solver:
    * Do you have to allocate and duplicate an entire board?
    * Can you re-use the board?
    * Can you get by with less information?
  * Consider what work you can avoid doing:
    * Are you doing any work early in the algorithm that you can tell will be fruitless?
    * How much work do you do on paths which are obviously wrong?
* Use [JSPerf](https://jsperf.com/) or [BenchmarkJS](https://benchmarkjs.com/) to benchmark your code. Use the results to improve your code. Notate changes in your commit messages
  * What symmetries in the chess board can you exploit to optimize your solution? Do it!
  * Implement a solution using bitwise operators
* Read some of these additional resources about bitwise operations:
  * [Wikipedia on bitwise operations](https://en.wikipedia.org/wiki/Bitwise_operation)
  * [C Programming tutorial on bitwise operators](https://www.cprogramming.com/tutorial/bitwise_operators.html)
  * This tutorial is in C, another programming language where bitwise operators are more common, but is also applicable to JavaScript.
[MDN on bitwise operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_Operators)
* Try devising your own bitshifting solution. How will you interact with the problem in bits?
* Implement [Martin Richards's bitwise n-queens solution algorithm](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.51.7113&rep=rep1&type=pdf), in JavaScript

*Optional*

* Play with Hack Reactor's own Ruan Pethiyagoda's [n-queens solution tweet](https://twitter.com/spellrp/status/332992908565295104) by either:
  * Writing a blog post that deciphers the tweet for a lay-programmer
  * Trying to improve on the speed of his algorithm without exceeding the character limit for a tweet

# NIGHTMARE MODE
[Parallelize](https://en.wikipedia.org/wiki/Parallel_computing) your solution then implement it using [HTML5 web workers](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Using_web_workers)
