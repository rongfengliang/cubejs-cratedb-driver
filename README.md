# cratedb-driver for cube.js

> fork form offical pg driver and do some change 

## Some Notes

current not merge info offical packages,should add some more config 
for cube.js

* .env

```code
CUBEJS_DB_HOST=localhost
CUBEJS_DB_NAME=doc
CUBEJS_DB_USER=crate
CUBEJS_DB_PASS=
CUBEJS_WEB_SOCKETS=true
CUBEJS_DEV_MODE=true
CUBEJS_DB_TYPE=cratedb
```

* cube.js

```code
const {CrateDBDriver,CrateDBQuery} = require("@dalongrong/cratedb-driver")
module.exports = {
    dialectFactory: (dataSource) => {
        // need config  datasource  for multitenant env
        return CrateDBQuery
    },
    dbType: ({ dataSource } = {}) => {
        return "cratedb"
    },
    driverFactory: ({ dataSource } = {}) => {
        return new CrateDBDriver({})
    }
};
```