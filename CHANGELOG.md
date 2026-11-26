# Changelog

## 1.0.0

**Release date:** TBD

Version 1.0.0 is the first release of `schema`, which runs on Lus 2.0.

- Added the `schema` package.
  - `schema.any`, `schema.string`, `schema.number`, `schema.integer`, `schema.boolean`, and `schema.vector`: Return a schema that accepts values of one type.
  - `schema.literal` and `schema.oneof`: Return a schema that accepts one value or one of a list of values.
  - `schema.array`, `schema.tuple`, `schema.object`, and `schema.record`: Return a schema that accepts a table of a given shape.
  - `schema.union` and `schema.lazy`: Return a schema that accepts a value of any of several schemas, or of a schema that a function returns on first use.
  - `schema.coerce`: Holds versions of `string`, `number`, `integer`, and `boolean` that convert a string before checking it.
  - `schema:optional`, `schema:nullable`, and `schema:default`: Return a copy of a schema that accepts `nil`.
  - `schema:min`, `schema:max`, `schema:length`, `schema:pattern`, and `schema:refine`: Return a copy of a schema with one more check.
  - `schema:transform`: Returns a copy of a schema whose parsed value passes through a function.
  - `schema:strict`, `schema:passthrough`, and `schema:catchall`: Return a copy of an object schema that rejects, keeps, or parses the keys its shape does not name.
  - `schema:extend` and `schema:partial`: Return a copy of an object schema with more fields or with every field optional.
  - `schema:describe`: Returns a copy of a schema with a description.
  - `schema:parse` and `schema:check`: Parse a value. `parse` raises an error object on failure and `check` returns it.
  - `schema:compiled` and `schema.error`: Return the compiled check of a schema and build an error object from its issues.
  - `schema:serializer`: Returns a function that encodes a value of the schema as JSON.
  - `schema:json_schema`: Returns the JSON Schema of a schema.
  - `schema.iserror` and `schema.isschema`: Return true for an error object that `parse` raised and for a schema.
