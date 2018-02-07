---
title: "Peer Graded Assignment 2"
author: "Dan Brusic"
date: "January 31, 2018"
output: 
  ioslides_presentation: 
    keep_md: yes
---



## Comparing Super Bowl Winners and Losers
In this presentation we will briefly look at all 102 teams that have played in the past 51 super bowls (professional football championship in the United States) from the 1966 to 2016 seasons. The data comes from the website, [Pro Football Reference](https://www.pro-football-reference.com/). The data set contains all 102 super bowl teams and their regular season rank regarding their offensive and defensive yards per play.

## Load the Data
The `id` variable is the season year. The `wl` variable is whether that team won or lost the super bowl (represented by a 1 and 0 respectively). 

```r
df = read.csv("superbowlODranks.csv")
df = df[,-1]
rbind(df[1:4,], df[52:55,])
```

```
     id                  .Tm Ro.yardsperplayrank Rd.yardsperplayrank wl
1  2016 New England Patriots                   6                  10  1
2  2015       Denver Broncos                  19                   1  1
3  2014 New England Patriots                  13                  11  1
4  2013     Seattle Seahawks                   9                   1  1
52 2016      Atlanta Falcons                   1                  22  0
53 2015    Carolina Panthers                  13                   2  0
54 2014     Seattle Seahawks                   6                   1  0
55 2013       Denver Broncos                   2                  16  0
```

## Making the Plot
The next slide plots all 51 super bowl winners and the number of ranks ahead of their opponent they were. In other words, each winning team's offensive and defensive ranks were subtracted from their super bowl opponent's ranks.

```r
odiff = df$Ro.yardsperplayrank[52:102] - df$Ro.yardsperplayrank[1:51]
ddiff = df$Rd.yardsperplayrank[52:102] - df$Rd.yardsperplayrank[1:51]
```

## Making the Plot
The x and y coordinates for each winning team are `odiff` and `ddiff` respectively. The plot allows you to highlight each of the four quadrants.

- Quadrant 1: Teams that had both a better offense and defense.
- Quadrant 2: Teams that only had a better defense.
- Quadrant 3: Teams that had both a worse offense and worse defense.
- Quadrant 4: Teams that had only a better offense.


## Plot of Super Bowl Winners


<!--html_preserve--><div id="htmlwidget-4fb5c27f78d01789915f" style="width:720px;height:432px;" class="plotly html-widget"></div>
<script type="application/json" data-for="htmlwidget-4fb5c27f78d01789915f">{"x":{"visdat":{"97868b777c3":["function () ","plotlyVisDat"]},"cur_data":"97868b777c3","attrs":{"97868b777c3":{"x":[-5,-6,-7,-7,-13,-4,5,1,-18,-18,19,-8,-3,-3,-24,-19,-7,8,1,-1,9,11,8,14,2,-2,-16,21,-3,4,-1,4,-1,-8,7,-17,-13,17,-8,13,12,1,-8,7,2,2,-5,9,-1,-5,-8],"y":[12,1,-10,15,-7,6,-8,-13,16,-1,-27,9,-1,3,10,-16,4,18,2,-10,16,-5,6,9,7,9,3,-3,8,8,3,3,4,21,-6,11,-5,2,-1,3,-8,1,10,12,1,3,-4,-1,-1,-2,4],"mode":"markers","marker":{"size":9,"color":"lightgreen","line":{"color":"darkgreen","width":2}},"text":["2016 <br> New England Patriots","2015 <br> Denver Broncos","2014 <br> New England Patriots","2013 <br> Seattle Seahawks","2012 <br> Baltimore Ravens","2011 <br> New York Giants","2010 <br> Green Bay Packers","2009 <br> New Orleans Saints","2008 <br> Pittsburgh Steelers","2007 <br> New York Giants","2006 <br> Indianapolis Colts","2005 <br> Pittsburgh Steelers","2004 <br> New England Patriots","2003 <br> New England Patriots","2002 <br> Tampa Bay Buccaneers","2001 <br> New England Patriots","2000 <br> Baltimore Ravens","1999 <br> St. Louis Rams","1998 <br> Denver Broncos","1997 <br> Denver Broncos","1996 <br> Green Bay Packers","1995 <br> Dallas Cowboys","1994 <br> San Francisco 49ers","1993 <br> Dallas Cowboys","1992 <br> Dallas Cowboys","1991 <br> Washington Redskins","1990 <br> New York Giants","1989 <br> San Francisco 49ers","1988 <br> San Francisco 49ers","1987 <br> Washington Redskins","1986 <br> New York Giants","1985 <br> Chicago Bears","1984 <br> San Francisco 49ers","1983 <br> Los Angeles Raiders","1982 <br> Washington Redskins","1981 <br> San Francisco 49ers","1980 <br> Oakland Raiders","1979 <br> Pittsburgh Steelers","1978 <br> Pittsburgh Steelers","1977 <br> Dallas Cowboys","1976 <br> Oakland Raiders","1975 <br> Pittsburgh Steelers","1974 <br> Pittsburgh Steelers","1973 <br> Miami Dolphins","1972 <br> Miami Dolphins","1971 <br> Dallas Cowboys","1970 <br> Baltimore Colts","1969 <br> Kansas City Chiefs","1968 <br> New York Jets","1967 <br> Green Bay Packers","1966 <br> Green Bay Packers"],"alpha":1,"sizes":[10,100],"type":"scatter"}},"layout":{"margin":{"b":40,"l":60,"t":25,"r":10},"xaxis":{"domain":[0,1],"title":"Offensive Ranks Ahead of Opponent"},"yaxis":{"domain":[0,1],"title":"Defensive Ranks Ahead of Opponent"},"showlegend":false,"updatemenus":[{"active":-1,"type":"buttons","xanchor":"center","yanchor":"top","x":1.2,"y":0.9,"buttons":[{"label":"None","method":"relayout","args":[{"shapes":[]}]},{"label":"1","method":"relayout","args":[{"shapes":[{"type":"rect","xref":"x","yref":"y","x0":0,"y0":0,"x1":19,"y1":19,"opacity":0.25,"line":{"color":"blue"},"fillcolor":"blue"},[],[],[]]}]},{"label":"2","method":"relayout","args":[{"shapes":[[],{"type":"rect","xref":"x","yref":"y","x0":0,"y0":0,"x1":-25,"y1":22,"opacity":0.25,"line":{"color":"blue"},"fillcolor":"blue"},[],[]]}]},{"label":"3","method":"relayout","args":[{"shapes":[[],[],{"type":"rect","xref":"x","yref":"y","x0":0,"y0":0,"x1":-20,"y1":-17,"opacity":0.25,"line":{"color":"blue"},"fillcolor":"blue"},[]]}]},{"label":"4","method":"relayout","args":[{"shapes":[[],[],[],{"type":"rect","xref":"x","yref":"y","x0":0,"y0":0,"x1":22,"y1":-28,"opacity":0.25,"line":{"color":"blue"},"fillcolor":"blue"}]}]}]}],"hovermode":"closest"},"source":"A","config":{"modeBarButtonsToAdd":[{"name":"Collaborate","icon":{"width":1000,"ascent":500,"descent":-50,"path":"M487 375c7-10 9-23 5-36l-79-259c-3-12-11-23-22-31-11-8-22-12-35-12l-263 0c-15 0-29 5-43 15-13 10-23 23-28 37-5 13-5 25-1 37 0 0 0 3 1 7 1 5 1 8 1 11 0 2 0 4-1 6 0 3-1 5-1 6 1 2 2 4 3 6 1 2 2 4 4 6 2 3 4 5 5 7 5 7 9 16 13 26 4 10 7 19 9 26 0 2 0 5 0 9-1 4-1 6 0 8 0 2 2 5 4 8 3 3 5 5 5 7 4 6 8 15 12 26 4 11 7 19 7 26 1 1 0 4 0 9-1 4-1 7 0 8 1 2 3 5 6 8 4 4 6 6 6 7 4 5 8 13 13 24 4 11 7 20 7 28 1 1 0 4 0 7-1 3-1 6-1 7 0 2 1 4 3 6 1 1 3 4 5 6 2 3 3 5 5 6 1 2 3 5 4 9 2 3 3 7 5 10 1 3 2 6 4 10 2 4 4 7 6 9 2 3 4 5 7 7 3 2 7 3 11 3 3 0 8 0 13-1l0-1c7 2 12 2 14 2l218 0c14 0 25-5 32-16 8-10 10-23 6-37l-79-259c-7-22-13-37-20-43-7-7-19-10-37-10l-248 0c-5 0-9-2-11-5-2-3-2-7 0-12 4-13 18-20 41-20l264 0c5 0 10 2 16 5 5 3 8 6 10 11l85 282c2 5 2 10 2 17 7-3 13-7 17-13z m-304 0c-1-3-1-5 0-7 1-1 3-2 6-2l174 0c2 0 4 1 7 2 2 2 4 4 5 7l6 18c0 3 0 5-1 7-1 1-3 2-6 2l-173 0c-3 0-5-1-8-2-2-2-4-4-4-7z m-24-73c-1-3-1-5 0-7 2-2 3-2 6-2l174 0c2 0 5 0 7 2 3 2 4 4 5 7l6 18c1 2 0 5-1 6-1 2-3 3-5 3l-174 0c-3 0-5-1-7-3-3-1-4-4-5-6z"},"click":"function(gd) { \n        // is this being viewed in RStudio?\n        if (location.search == '?viewer_pane=1') {\n          alert('To learn about plotly for collaboration, visit:\\n https://cpsievert.github.io/plotly_book/plot-ly-for-collaboration.html');\n        } else {\n          window.open('https://cpsievert.github.io/plotly_book/plot-ly-for-collaboration.html', '_blank');\n        }\n      }"}],"cloud":false},"data":[{"x":[-5,-6,-7,-7,-13,-4,5,1,-18,-18,19,-8,-3,-3,-24,-19,-7,8,1,-1,9,11,8,14,2,-2,-16,21,-3,4,-1,4,-1,-8,7,-17,-13,17,-8,13,12,1,-8,7,2,2,-5,9,-1,-5,-8],"y":[12,1,-10,15,-7,6,-8,-13,16,-1,-27,9,-1,3,10,-16,4,18,2,-10,16,-5,6,9,7,9,3,-3,8,8,3,3,4,21,-6,11,-5,2,-1,3,-8,1,10,12,1,3,-4,-1,-1,-2,4],"mode":"markers","marker":{"fillcolor":"rgba(31,119,180,1)","color":"lightgreen","size":9,"line":{"color":"darkgreen","width":2}},"text":["2016 <br> New England Patriots","2015 <br> Denver Broncos","2014 <br> New England Patriots","2013 <br> Seattle Seahawks","2012 <br> Baltimore Ravens","2011 <br> New York Giants","2010 <br> Green Bay Packers","2009 <br> New Orleans Saints","2008 <br> Pittsburgh Steelers","2007 <br> New York Giants","2006 <br> Indianapolis Colts","2005 <br> Pittsburgh Steelers","2004 <br> New England Patriots","2003 <br> New England Patriots","2002 <br> Tampa Bay Buccaneers","2001 <br> New England Patriots","2000 <br> Baltimore Ravens","1999 <br> St. Louis Rams","1998 <br> Denver Broncos","1997 <br> Denver Broncos","1996 <br> Green Bay Packers","1995 <br> Dallas Cowboys","1994 <br> San Francisco 49ers","1993 <br> Dallas Cowboys","1992 <br> Dallas Cowboys","1991 <br> Washington Redskins","1990 <br> New York Giants","1989 <br> San Francisco 49ers","1988 <br> San Francisco 49ers","1987 <br> Washington Redskins","1986 <br> New York Giants","1985 <br> Chicago Bears","1984 <br> San Francisco 49ers","1983 <br> Los Angeles Raiders","1982 <br> Washington Redskins","1981 <br> San Francisco 49ers","1980 <br> Oakland Raiders","1979 <br> Pittsburgh Steelers","1978 <br> Pittsburgh Steelers","1977 <br> Dallas Cowboys","1976 <br> Oakland Raiders","1975 <br> Pittsburgh Steelers","1974 <br> Pittsburgh Steelers","1973 <br> Miami Dolphins","1972 <br> Miami Dolphins","1971 <br> Dallas Cowboys","1970 <br> Baltimore Colts","1969 <br> Kansas City Chiefs","1968 <br> New York Jets","1967 <br> Green Bay Packers","1966 <br> Green Bay Packers"],"type":"scatter","xaxis":"x","yaxis":"y","frame":null}],"highlight":{"on":"plotly_click","persistent":false,"dynamic":false,"selectize":false,"opacityDim":0.2,"selected":{"opacity":1}},"base_url":"https://plot.ly"},"evals":["config.modeBarButtonsToAdd.0.click"],"jsHooks":{"render":[{"code":"function(el, x) { var ctConfig = crosstalk.var('plotlyCrosstalkOpts').set({\"on\":\"plotly_click\",\"persistent\":false,\"dynamic\":false,\"selectize\":false,\"opacityDim\":0.2,\"selected\":{\"opacity\":1}}); }","data":null}]}}</script><!--/html_preserve-->

## Further Notes

Out of the 51 winning super bowl teams (when compared to their super bowl opponents):

- 8 had only a better offense
- 18 had only a better defense
- 14 had a better offense and defense
- 11 had a worse offense and defense

