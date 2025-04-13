Right now I have copy & pasted some code in from two different projects that I want you to use as inspiration for making a new game.

`pages/grid_viewer.html`
Allows rendering a target and user submitted grid.
It does not actually accept these grids as inputs yet but instead just uses sample values.

`pages/code_editor.html`
Has a code edifor and game panel I copy & pasted from a previous project.
I want you to use this as inspiration for how you can integrate a code editor into the game.

`pages/pyodide.html`
Has an example of how to execute python code with the numpy package and get the result back in javascript.

`data/*/*.json`
Holds the data for the arc task grids.

I want to make a programming game that runs on a static website.
The aim of the game is to represent arc grids with as little code as possible.
For now just have users try and represent the first input grid in each arc task.

This will work by having a code editor panel on one side and a grid viewer panel on the other (see the html files I have provdided).
The code will be be executed using pyodide.

User programs will return a `list[list[int]]` grid which will be used to render the users output grid when they click run or hit `shift-enter`.

Unlike in my `pages/code_editor.html` example, lets just have everything run in a new `pages/game.html` file that holds the code for the code editor, grid viewer and code executor all in the one file.
