# schema

Describes the shape of a value and checks values against it, in the manner of zod.

```lus nocheck
local s = require("https://atmosp.here/2.0/schema.lus")

local Config = s.object({
    port = s.integer():min(1):max(65535),
    mode = s.oneof({ "dev", "prod" }),
})

local config = Config:parse({ port = 8080, mode = "dev" })
print(config.port)   --> 8080
```

The package requires Lus 2.0. It declares no permissions. It calls no `pledge` of its own, so the program that loads it keeps control of its permissions.

The reference is in the doc comments of `schema.lus`. Run `lus doc schema.lus` to print it.
