# JSONStat
A Tables.jl compliant for reading JSONStat files. Right now, only 'dataset' class is supported.
Output is a JSONStat.Datatable that can be loaded into a DataFrame, saved with CSV or use any other Tables.jl-ready package

### Example
```julia
using JSONStat, Dataframes
HTTP.get("https://json-stat.org/samples/us-gsp.json").body |> JSONStat.read |> DataFrame
```

Additional information can be accesed using:
     - ```JSONStat.dimensions(dt::JSONStat.Datatable)```
     - ```JSONStat.metadata(dt::JSONStat.Datatable)```

Both functions return nested dictionaries than can be pretty printed using ```JSONStat.pretty(d::Dict)```
