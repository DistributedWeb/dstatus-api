## Person `unwalled.garden/person`

---

 - Site type
 - **Description**: A human user.
 - **Path**: `/`

---

#### DWebX.json fields

The `/dwebx.json` file has the following fields:

|Key|Value|
|-|-|
|`type`|`unwalled.garden/person`|
|`title`|The person's name|
|`description`|The person's short bio|

Example:

```json
{
  "type": "unwalled.garden/person",
  "title": "Alice",
  "description": "Advocate of the free and open web",
}
```

#### File structure

|Path|Type|
|-|-|
|`/dwebx.json`|Standard dwebx.json file|
|`/thumb.(png|jpg|jpeg)`|Profile picture|
|`/.data`|[Data directory](/dir/data)|
|`/.refs`|[Refs directory](/dir/refs)|