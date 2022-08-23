# PyPlot

Python の [Matplotlib](https://matplotlib.org/stable/index.html) を Julia で利用するためのインターフェース です。オリジナルの Matplotlib のほとんどの機能を利用することができます。

Matplotlib で描くことができる図の例は https://matplotlib.org/stable/gallery/index.html にあります。


## 利用例
```Julia
julia> using NetCDF
julia> v = ncread( "test.nc", "var1" )
julia> lon = ncread( "test.nc", "lon" )
julia> using PyPlot
julia> plot(lon, v[:,1,1,1])
```

## 参考
 * [PyPlot.jl](https://github.com/JuliaPy/PyPlot.jl)
 * [Julia早引きノート［23］JuliaでのMatplotlibによるグラフ描画](https://qiita.com/ttabata/items/96a0e172addfac690cca)
