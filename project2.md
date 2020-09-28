# 42-lem_in

## Goal

The goal of this project is to find the quickest way to get n ants across the farm.  

• Quickest way means the solution with the least number of lines, respecting the
output format requested below.  

• Obviously, there are some basic constraints. To be the first to arrive, ants will need
to take the shortest path (and that isn’t necessarily the simplest). They will also
need to avoid traffic jams as well as walking all over their fellow ants.  

• At the beginning of the game, all the ants are in the room ##start. The goal is
to bring them to the room ##end with as few turns as possible. Each room can
only contain one ant at a time. (except at ##start and ##end which can contain
as many ants as necessary.)  

• We consider that all the ants are in the room ##start at the beginning of the game.  

• At each turn you will only display the ants that moved.  

• At each turn you can move each ant only once and through a tube (the room at
the receiving end must be empty).  

• You must to display your results on the standard output in the following format:
```
number_of_ants
the_rooms
the_links
Lx-y Lz-w Lr-o ...
```
Lx, Lz, Lr represents the ants’ numbers (going from 1 to number_of_ants) and second part after
hyphen represents the rooms’ names.  

***!!*** These are maps with sometimes more than 10,000 lines, the way you
read and write data must also be fairly fast.

## Instructions

• Your program will receive the data describing the ant farm from the standard output
in the following format:  

```
number_of_ants
the_rooms
the_links
```

• The ant farm is defined by the following links:

```
##start
1 23 3
2 16 7
#comment
3 16 3
4 16 5
5 9 3
6 1 5
7 4 8
##end
0 9 5
0-4
0-6
1-3
4-3
5-2
3-5
#another comment
4-2
2-1
7-6
7-2
7-4
6-5
#another comment
```
• There are two parts:  
  ◦ The rooms, which are defined by: name coord_x coord_y  
  ◦ The links, which are defined by: name1-name2  
  ◦ All of it is broken by comments, which start with #  

## Data structure

I used hash table to create connections between rooms (I can jump from room to room immediately instead of going through a list of rooms each time I need to create a new connection.)   

I stored rest of the input data in linked lists (rooms, links, map, paths etc).

## Error handling

As always error management must be flawless. This means that the input is valid and there must be enough data to process normally. So I have to check that input comes in right order ants->rooms->links and everything is in right format. If not my program show specific error message and also the line where error occurs.

![error](/images/error.png)

## Algorithm

I used breadth first search (BFS) to find shortest path. At some graphs and with certain amount of ants the shortest path isn't necessarily the best solution (see the example below). Shortest path might also block BFS from finding other paths if we only observe vertexes (can't visit same vertex twise). So I lent an idea from Edmonds-Karp algorithm to take advantage of flows as well. Now I can check if edge is valid through parent vertex to child vertex. That allows my algorithm to find other paths as well on certain maps.  
  
I have also defined weight for every vertex wich means the distance from the start. If some vertex belongs to other path I compare it's current weight to it's potential weight and if the potential weight (parent vertex weight + 1) is smaller I can add that vertex to queue.  
  
If I run my program with the graph below after first iterations (4 ants), I will use 6 moves. After second iterations I need to use only 5 moves.

![flow](/images/flow.png)

## Bonuses

-e print specific error message  
-p print paths and number of lines  
-c print colors  

## Compiling and Usage

usage: ``./lem-in [[-p][-c][-e]] < [source file]``  
-p flag for printing paths with colors (mind that program is faster without -p flag because I use my own printft to print colors and otherwise just write)

clone and compile: you can clone and compile the program on your terminal:
```git clone https://github.com/kurval/42-lem_in.git lem_in && cd lem_in && make```  

## Example

![example](/images/print_screen.png)

## Sources
https://medium.com/tebs-lab/types-of-graphs-7f3891303ea8  
https://www.tutorialspoint.com/data_structures_algorithms/hash_table_program_in_c.htm  
https://www.youtube.com/watch?v=RppuJYwlcI8  
https://www.geeksforgeeks.org/breadth-first-search-or-bfs-for-a-graph/  

For more details view my github account: 
<a href="https://github.com/kurval/42-lem_in?raw=true" target="_blank">GitHub Source</a>
  
<p>
<a href="#" title="frontpage" class="text-decoration-none">
<svg width="1em" height="1em" viewBox="0 0 16 16" class="bi bi-arrow-left-circle" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
  <path fill-rule="evenodd" d="M8 15A7 7 0 1 0 8 1a7 7 0 0 0 0 14zm0 1A8 8 0 1 0 8 0a8 8 0 0 0 0 16z"/>
  <path fill-rule="evenodd" d="M12 8a.5.5 0 0 1-.5.5H5.707l2.147 2.146a.5.5 0 0 1-.708.708l-3-3a.5.5 0 0 1 0-.708l3-3a.5.5 0 1 1 .708.708L5.707 7.5H11.5a.5.5 0 0 1 .5.5z"/>
</svg>
Back to front page
</a>
</p>
