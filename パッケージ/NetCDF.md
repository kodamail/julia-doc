# NetCDF

## 情報取得
```Julia
ncinfo( filename )
```

## データの読み込み
```Julia
vararray = ncread(filename, varname )
```



## メモ
元のファイルが存在する場合、ncwrite等すると追記されるので注意。

## 参考
 * [NetCDF.jl](https://juliageo.org/NetCDF.jl/dev/quickstart/)
