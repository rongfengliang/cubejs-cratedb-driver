# cratedb-driver for cube.js

> fork form offical pg driver and do some change 

## Some Notes

current not merge info offical packages,should add some more config 
for cube.js

```code
const CrateDBQuery = require("./CrateDBQuery")
dialectFactory: (dataSource) => {
    // need config  datasource  for multitenant env
    return CrateDBQuery
},
```