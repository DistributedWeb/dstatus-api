## DVaults `unwalled.garden/dvaults`

---

 - File type
 - **Description**: A list of dvaults.
 - **Path**: `/.data/dvaults.json`

---

#### Example

```json
{
  "type": "unwalled.garden/dvaults",
  "dvaults": [
    {
      "key":  "0529130af0258e7fb30bf5a0a3f73d69b343dfc9f23fdded8cc7c01c71c0702a",
      "title": "Paul Frazee",
      "description": "DBrowserX guy",
      "type": ["unwalled.garden/person"]
    },
    {
      "key": "43dfc9f23fdded8cc7c01c71c0702a0529130af0258e7fb30bf5a0a3f73d69b3",
      "title": "Unwalled Garden",
      "type": "unwalled.garden/website"
    }
  ]
}
```

#### Schema

```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "$id": "dwebx://unwalled.garden/dvaults.json",
  "type": "object",
  "title": "DVaults",
  "description": "A list of dvaults.",
  "required": [
    "type",
    "dvaults"
  ],
  "properties": {
    "type": {
      "type": "string",
      "description": "The object's type",
      "const": "unwalled.garden/dvaults"
    },
    "dvaults": {
      "type": "array",
      "items": {
        "type": "object",
        "required": ["key"],
        "properties": {
          "key": {
            "type": "string",
            "pattern": "^[0-9a-f]{64}$"
          },
          "title": {
            "type": "string"
          },
          "description": {
            "type": "string"
          },
          "type": {
            "type": "string"
          }
        }
      }
    }
  }
}
```