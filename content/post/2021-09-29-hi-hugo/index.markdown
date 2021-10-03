---
title: Hi Hugo
author: ''
date: '2021-09-29'
slug: hi-hugo
categories: []
tags: []
subtitle: ''
summary: ''
authors: []
lastmod: '2021-09-29T20:18:21-04:00'
featured: no
image:
  caption: ''
  focal_point: ''
  preview_only: no
projects: []
---

<script src="{{< blogdown/postref >}}index_files/htmlwidgets/htmlwidgets.js"></script>
<script src="{{< blogdown/postref >}}index_files/plotly-binding/plotly.js"></script>
<script src="{{< blogdown/postref >}}index_files/typedarray/typedarray.min.js"></script>
<script src="{{< blogdown/postref >}}index_files/jquery/jquery.min.js"></script>
<link href="{{< blogdown/postref >}}index_files/crosstalk/css/crosstalk.css" rel="stylesheet" />
<script src="{{< blogdown/postref >}}index_files/crosstalk/js/crosstalk.min.js"></script>
<link href="{{< blogdown/postref >}}index_files/plotly-htmlwidgets-css/plotly-htmlwidgets.css" rel="stylesheet" />
<script src="{{< blogdown/postref >}}index_files/plotly-main/plotly-latest.min.js"></script>

Here goes nothing!

``` r
library(data.table)
library(tidyverse)
library(ggplot2)
library(readxl)
library(viridis)
```

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-2-1.png" width="672" />

``` r
library(knitr)
kable(head(chess))
```

| name           | age | country | continent | curclass | currapid | curblitz | y10rating | y12rating | y14rating | y16rating | y18rating | y20rating |
|:---------------|----:|:--------|:----------|---------:|---------:|---------:|----------:|----------:|----------:|----------:|----------:|----------:|
| Carlsen        |  29 | NOR     | EUR       |     2872 |     2881 |     2887 |      2084 |      2450 |      2570 |      2714 |      2801 |      2826 |
| Caruana        |  27 | USA     | AME       |     2822 |     2773 |     2711 |      2165 |      2381 |      2549 |      2670 |      2721 |      2796 |
| Ding           |  27 | CHN     | ASI       |     2805 |     2836 |     2788 |        NA |      2289 |      2395 |      2530 |      2665 |      2722 |
| Grischuk       |  36 | RUS     | EUR       |     2777 |     2784 |     2765 |        NA |      2375 |      2490 |      2606 |      2702 |      2732 |
| Nepomniachtchi |  29 | RUS     | EUR       |     2774 |     2736 |     2779 |      2243 |      2432 |      2505 |      2613 |      2632 |      2733 |
| Aronian        |  37 | ARM     | EUR       |     2773 |     2778 |     2740 |        NA |      2355 |      2435 |      2518 |      2587 |      2649 |

    ## 
    ## Attaching package: 'plotly'

    ## The following object is masked from 'package:ggplot2':
    ## 
    ##     last_plot

    ## The following object is masked from 'package:stats':
    ## 
    ##     filter

    ## The following object is masked from 'package:graphics':
    ## 
    ##     layout

<div id="htmlwidget-1" style="width:672px;height:480px;" class="plotly html-widget"></div>
<script type="application/json" data-for="htmlwidget-1">{"x":{"data":[{"orientation":"v","width":0.9,"base":0,"x":[1],"y":[2610],"text":"name: Anand<br />y20rating: 2610<br />name: Anand","type":"bar","marker":{"autocolorscale":false,"color":"rgba(68,1,84,1)","line":{"width":1.88976377952756,"color":"transparent"}},"name":"Anand","legendgroup":"Anand","showlegend":true,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null},{"orientation":"v","width":0.9,"base":0,"x":[2],"y":[2649],"text":"name: Aronian<br />y20rating: 2649<br />name: Aronian","type":"bar","marker":{"autocolorscale":false,"color":"rgba(49,104,142,1)","line":{"width":1.88976377952756,"color":"transparent"}},"name":"Aronian","legendgroup":"Aronian","showlegend":true,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null},{"orientation":"v","width":0.9,"base":0,"x":[3],"y":[2826],"text":"name: Carlsen<br />y20rating: 2826<br />name: Carlsen","type":"bar","marker":{"autocolorscale":false,"color":"rgba(53,183,121,1)","line":{"width":1.88976377952756,"color":"transparent"}},"name":"Carlsen","legendgroup":"Carlsen","showlegend":true,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null},{"orientation":"v","width":0.9,"base":0,"x":[4],"y":[2796],"text":"name: Caruana<br />y20rating: 2796<br />name: Caruana","type":"bar","marker":{"autocolorscale":false,"color":"rgba(253,231,37,1)","line":{"width":1.88976377952756,"color":"transparent"}},"name":"Caruana","legendgroup":"Caruana","showlegend":true,"xaxis":"x","yaxis":"y","hoverinfo":"text","frame":null}],"layout":{"margin":{"t":26.2283105022831,"r":7.30593607305936,"b":40.1826484018265,"l":48.9497716894977},"font":{"color":"rgba(0,0,0,1)","family":"","size":14.6118721461187},"xaxis":{"domain":[0,1],"automargin":true,"type":"linear","autorange":false,"range":[0.4,4.6],"tickmode":"array","ticktext":["Anand","Aronian","Carlsen","Caruana"],"tickvals":[1,2,3,4],"categoryorder":"array","categoryarray":["Anand","Aronian","Carlsen","Caruana"],"nticks":null,"ticks":"","tickcolor":null,"ticklen":3.65296803652968,"tickwidth":0,"showticklabels":true,"tickfont":{"color":"rgba(77,77,77,1)","family":"","size":11.689497716895},"tickangle":-0,"showline":false,"linecolor":null,"linewidth":0,"showgrid":true,"gridcolor":"rgba(235,235,235,1)","gridwidth":0.66417600664176,"zeroline":false,"anchor":"y","title":{"text":"name","font":{"color":"rgba(0,0,0,1)","family":"","size":14.6118721461187}},"hoverformat":".2f"},"yaxis":{"domain":[0,1],"automargin":true,"type":"linear","autorange":false,"range":[-141.3,2967.3],"tickmode":"array","ticktext":["0","1000","2000"],"tickvals":[0,1000,2000],"categoryorder":"array","categoryarray":["0","1000","2000"],"nticks":null,"ticks":"","tickcolor":null,"ticklen":3.65296803652968,"tickwidth":0,"showticklabels":true,"tickfont":{"color":"rgba(77,77,77,1)","family":"","size":11.689497716895},"tickangle":-0,"showline":false,"linecolor":null,"linewidth":0,"showgrid":true,"gridcolor":"rgba(235,235,235,1)","gridwidth":0.66417600664176,"zeroline":false,"anchor":"x","title":{"text":"y20rating","font":{"color":"rgba(0,0,0,1)","family":"","size":14.6118721461187}},"hoverformat":".2f"},"shapes":[{"type":"rect","fillcolor":null,"line":{"color":null,"width":0,"linetype":[]},"yref":"paper","xref":"paper","x0":0,"x1":1,"y0":0,"y1":1}],"showlegend":true,"legend":{"bgcolor":null,"bordercolor":null,"borderwidth":0,"font":{"color":"rgba(0,0,0,1)","family":"","size":11.689497716895},"y":0.96751968503937},"annotations":[{"text":"name","x":1.02,"y":1,"showarrow":false,"ax":0,"ay":0,"font":{"color":"rgba(0,0,0,1)","family":"","size":14.6118721461187},"xref":"paper","yref":"paper","textangle":-0,"xanchor":"left","yanchor":"bottom","legendTitle":true}],"hovermode":"closest","barmode":"relative"},"config":{"doubleClick":"reset","showSendToCloud":false},"source":"A","attrs":{"a1447afb10":{"x":{},"y":{},"fill":{},"type":"bar"}},"cur_data":"a1447afb10","visdat":{"a1447afb10":["function (y) ","x"]},"highlight":{"on":"plotly_click","persistent":false,"dynamic":false,"selectize":false,"opacityDim":0.2,"selected":{"opacity":1},"debounce":0},"shinyEvents":["plotly_hover","plotly_click","plotly_selected","plotly_relayout","plotly_brushed","plotly_brushing","plotly_clickannotation","plotly_doubleclick","plotly_deselect","plotly_afterplot","plotly_sunburstclick"],"base_url":"https://plot.ly"},"evals":[],"jsHooks":[]}</script>
