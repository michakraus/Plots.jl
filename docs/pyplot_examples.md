### Lines

A simple line plot of the 3 columns.

```julia
plot(rand(100,3))
```

![](../img/pyplot/pyplot_example_1.png)

### Functions

Plot multiple functions.

```julia
plot(0:0.01:4π,[sin,cos])
```

![](../img/pyplot/pyplot_example_2.png)

### 

You can also call it with plot(f, xmin, xmax).

```julia
plot([sin,cos],0,4π)
```

![](../img/pyplot/pyplot_example_3.png)

### 

Or make a parametric plot with plot(fx, fy, umin, umax).

```julia
plot(sin,(x->begin  # /Users/tom/.julia/v0.4/Plots/docs/example_generation.jl, line 33:
            sin(2x)
        end),0,2π)
```

![](../img/pyplot/pyplot_example_4.png)

### Global

Change the guides/background without a separate call.

```julia
plot(rand(10); title="TITLE",xlabel="XLABEL",ylabel="YLABEL",background_color=RGB(0.5,0.5,0.5))
```

![](../img/pyplot/pyplot_example_5.png)

### Two-axis

Use the `axis` or `axiss` arguments.

Note: This is only supported with Qwt right now

```julia
plot(Vector[randn(100),randn(100) * 100]; axiss=[:left,:right],ylabel="LEFT",yrightlabel="RIGHT")
```

![](../img/pyplot/pyplot_example_6.png)

### Vectors w/ pluralized args

Plot multiple series with different numbers of points.  Mix arguments that apply to all series (singular... see `marker`) with arguments unique to each series (pluralized... see `colors`).

```julia
plot(Vector[rand(10),rand(20)]; marker=:ellipse,markersize=8,colors=[:red,:blue])
```

![](../img/pyplot/pyplot_example_7.png)

### Build plot in pieces

Start with a base plot...

```julia
plot(rand(100) / 3; reg=true,fillto=0)
```

![](../img/pyplot/pyplot_example_8.png)

### 

and add to it later.

```julia
scatter!(rand(100); markersize=6,color=:blue)
```

![](../img/pyplot/pyplot_example_9.png)

### Heatmaps



```julia
heatmap(randn(10000),randn(10000); nbins=100)
```

![](../img/pyplot/pyplot_example_10.png)

### Lots of line types

Options: (:line, :step, :stepinverted, :sticks, :scatter, :none, :heatmap, :hexbin, :hist, :bar)  
Note: some may not work with all backends

```julia
plot(rand(20,4); linetypes=[:line,:step,:sticks,:scatter],labels=["line","step","sticks","dots"])
```

![](../img/pyplot/pyplot_example_11.png)

### Lots of line styles

Options: (:solid, :dash, :dot, :dashdot, :dashdotdot)  
Note: some may not work with all backends

```julia
plot(rand(20,5); linestyles=[:solid,:dash,:dot,:dashdot,:dashdotdot],labels=["solid","dash","dot","dashdot","dashdotdot"])
```

![](../img/pyplot/pyplot_example_12.png)

### Lots of marker types

Options: (:none, :ellipse, :rect, :diamond, :utriangle, :dtriangle, :cross, :xcross, :star1, :star2, :hexagon)  
Note: some may not work with all backends

```julia
plot(repmat(collect(1:10)',10,1); markers=[:ellipse,:rect,:diamond,:utriangle,:dtriangle,:cross,:xcross,:star1,:star2,:hexagon],labels=["ellipse","rect","diamond","utriangle","dtriangle","cross","xcross","star1","star2","hexagon"],linetype=:none,markersize=10)
```

![](../img/pyplot/pyplot_example_13.png)

### Bar

x is the midpoint of the bar. (todo: allow passing of edges instead of midpoints)

```julia
bar(randn(1000))
```

![](../img/pyplot/pyplot_example_14.png)

### Histogram

note: fillto isn't supported on all backends

```julia
histogram(randn(1000); nbins=50,fillto=20)
```

![](../img/pyplot/pyplot_example_15.png)
