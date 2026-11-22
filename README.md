# schema

`schema` describes the shape of a value and checks values against it, reporting every issue with its path. Its API follows the TypeScript library zod.

The following example checks the configuration of a server.

```lus nocheck
local s = require("https://atmosp.here/2.0/schema.lus")

local Config = s.object({
    port = s.integer():min(1):max(65535),
    mode = s.oneof({ "dev", "prod" }),
})

local config = Config:parse({ port = 8080, mode = "dev" })
print(config.port)   --> 8080
```

The package requires Lus 2.0 and declares no permissions. It never calls `pledge`, so the program that loads it keeps control of its permissions.

The reference is in the doc comments of `schema.lus`, which `lus doc schema.lus` prints.
