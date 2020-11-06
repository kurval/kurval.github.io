# 42-FdF

![preview_gif](/images/preview_fdf.gif)  
*Visualizing “iron wire” meshing in 3D*  

## About  

This project is about creating a simplified graphic “wireframe” (“fils de fer” in french,
hence the name of the project) representation of a relief landscape linking various points
(x, y, z) via segments. The coordinates of this landscape are stored in a file passed as
a parameter to your program. Here is an example:  

```
$>cat 42.fdf
0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0
0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0
0  0 10 10  0  0 10 10  0  0  0 10 10 10 10 10  0  0  0
0  0 10 10  0  0 10 10  0  0  0  0  0  0  0 10 10  0  0
0  0 10 10  0  0 10 10  0  0  0  0  0  0  0 10 10  0  0
0  0 10 10 10 10 10 10  0  0  0  0 10 10 10 10  0  0  0
0  0  0 10 10 10 10 10  0  0  0 10 10  0  0  0  0  0  0
0  0  0  0  0  0 10 10  0  0  0 10 10  0  0  0  0  0  0
0  0  0  0  0  0 10 10  0  0  0 10 10 10 10 10 10  0  0
0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0
0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0  0
$>
```  

Each number corresponds to a point in space:  
• The horizontal position corresponds to its axis.  
• The vertical position corresponds to its ordinate.  
• The value corresponds to its altitude.  

## Implementation  

### Drawing a line  

In our school we will need to do everything from scratch. In this case it meant that we weren't given any line drawing function so we had to figure ourselves how to color pixels beetween line endpoints with help of [miniLibX library](https://qst0.github.io/ft_libgfx/man_mlx.html
). I used [Bresenham's line algorithm](https://en.wikipedia.org/wiki/Bresenham%27s_line_algorithm) for drawing a line which was the most obvious choice.

### Colors  

I used the folowing color scale according to altitude:  

![color_scale](/images/COLORS.png)

### Projections  

In this project we must have 2 type of projection but we were free to choose the type of projection:
parallel, iso, conic.  

I chose to use isometric and conic. Also I added dimetric projections which was very easy to implement from isometric projection (30 degree angle -> 15).  

## Controls  

I have the following controls to help user to view different maps:  

• Rotation around the axis: Arrow Keys  
• Change projections: 1 = ISO 2 = DIMETRIC 3 = CONIC  
• Zooming in and out: Mouse sroll  
• Moving the map on the screen: Right click  
• Change color mode (default white): 'C' key  
• Reset map values: 'D' key  

![preview_japan](/images/japan_iso.png)  
*Isometric projection of Japan*  

Using graphic library: miniLibX  
https://qst0.github.io/ft_libgfx/man_mlx.html

For more details view my 
<a href="https://github.com/kurval/42-fdf?raw=true" target="_blank">GitHub</a>

<p>
<a href="https://kurval.github.io/" title="frontpage" class="text-decoration-none">
<svg width="2em" height="2em" viewBox="0 0 16 16" class="bi bi-arrow-left-circle-fill" fill="black" xmlns="http://www.w3.org/2000/svg">
  <path fill-rule="evenodd" d="M16 8A8 8 0 1 1 0 8a8 8 0 0 1 16 0zm-4.5.5a.5.5 0 0 0 0-1H5.707l2.147-2.146a.5.5 0 1 0-.708-.708l-3 3a.5.5 0 0 0 0 .708l3 3a.5.5 0 0 0 .708-.708L5.707 8.5H11.5z"/>
</svg>
<br>Go back to home page
</a>
</p>
