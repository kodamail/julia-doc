# WriteVTK
ParaView などで読み込める VTK XML 形式のデータを出力するためのモジュールです。

## 利用例（POLYGON）
```Julia
julia> using WriteVTK

julia> points = rand(3,5)
3×5 Array{Float64,2}:
 0.142484  0.240401   0.0483133  0.369176  0.728685
 0.97762   0.756289   0.243123   0.210937  0.443229
 0.257937  0.0618145  0.932194   0.530909  0.0081726

julia> cells=Array{MeshCell{VTKCellType,Array{Int64,1}}}(undef,2)
2-element Array{MeshCell{VTKCellType,Array{Int64,1}},1}:
 #undef
 #undef

julia> cells[1]=MeshCell(VTKCellTypes.VTK_POLYGON, [ 1, 3, 2 ])
MeshCell{VTKCellType,Array{Int64,1}}(VTKCellType("VTK_POLYGON", 0x07, -1), [1, 3, 2])

julia> cells[2]=MeshCell(VTKCellTypes.VTK_POLYGON, [ 1, 2, 3, 5, 4])
MeshCell{VTKCellType,Array{Int64,1}}(VTKCellType("VTK_POLYGON", 0x07, -1), [1, 2, 3, 5, 4])

julia> vtk_grid("aaa", points, cells) do vtk
       vtk["var1"]=rand(length(cells))
       end
1-element Array{String,1}:
 "aaa.vtu"
```

## 参考
 * [WriteVTK.jl](https://juliavtk.github.io/WriteVTK.jl/stable/)
