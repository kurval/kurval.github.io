# FILLIT

![fillit_gif](https://j.gifs.com/4Q3L2J.gif)  

## Goal

Our goal was to create a program which takes only one parameter (source file) containing a list of Tetriminos
to assemble. Program needs to arrange every Tetriminos with each others in order to make
the ***smallest possible square***!

We split this project into three parts:

1. **Tetriminos validation** - to check that each tetriminos block is valid and create array of strings containing every block. If blocks are valid we can move to section two. Else the program returns error message.
2. **Creating array of structs** - which we need in section three. Single struct containing coordinations of tetrimino's '#' -characters. Along with coordinations we assign alphabet to identify each tetrimino piece starting with 'A'.
3. **Solving the smallest square** - in this section we used recursive backtracking method to solve this puzzle. In this part we can use coordinations from previous part to check if the current place is empty in our map. If place is not empty we are going to remove current piece and place it to next spot on our map. After we have tried first peace to every spot and if there is no solution we are going resize our map bigger and continue as long as we find the solution (smallest square).

## Compiling and Usage

Run **make** from terminal and use following command **./fillit [source file]**.
## Example

tetriminos.txt:

```
....
##..
.#..
.#..

....
####
....
....

#...
###.
....
....

....
##..
.##.
....
```

execution:
```
~ make
~ ./fillit tetriminos.txt 

DDAA
CDDA
CCCA
BBBB
```
OR you can just paste this on your terminal: git clone https://github.com/kurval/42-fillit.git fillit && cd fillit && make && ./fillit tetriminos.txt  
  
For more details view my github account: 
<a href="https://github.com/kurval/42-fillit?raw=true" target="_blank">GitHub Source</a> 
  
<p>
<a href="https://kurval.github.io/" title="frontpage" class="text-decoration-none">
<svg width="2em" height="2em" viewBox="0 0 16 16" class="bi bi-arrow-left-circle-fill" fill="black" xmlns="http://www.w3.org/2000/svg">
  <path fill-rule="evenodd" d="M16 8A8 8 0 1 1 0 8a8 8 0 0 1 16 0zm-4.5.5a.5.5 0 0 0 0-1H5.707l2.147-2.146a.5.5 0 1 0-.708-.708l-3 3a.5.5 0 0 0 0 .708l3 3a.5.5 0 0 0 .708-.708L5.707 8.5H11.5z"/>
</svg>
<br>Go back to home page
</a>
</p>
