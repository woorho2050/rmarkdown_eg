rmarkdown example
================
woorho2050
2020.05.31.

# artful plotting

``` r
library(flametree)
library(voronoise)
```

    ## Loading required package: ggplot2

    ## Loading required package: ggforce

``` r
library(deldir)
```

    ## deldir 0.1-25

``` r
ft <- flametree_grow(333, 4, 0.5 + (1:5) / 9, c(-20, 15, 30), 4)

ggplot(ft[ft$id_leaf, ], aes(coord_x, coord_y)) +
    geom_bezier(aes(group = id_path), ft) +
    geom_point(size = 3) +
    geom_voronoise(aes(fill = seg_col), max.radius = 0.2) +
    theme_void() +
    coord_equal()
```

    ## Warning: stat_voronoi_tile: dropping duplicated points

![](rmarkdown_eg_files/figure-gfm/unnamed-chunk-1-1.png)<!-- -->
