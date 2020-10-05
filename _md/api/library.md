## Library API

An API for dvaults that have been saved locally and/or published on the network.

---

```js
import { library } from 'dwebx://unwalled.garden/index.js'

// read
await library.list({
  authors,
  types,
  keys,
  isSaved,
  isHosting,
  visibility,
  forkOf,
  isOwner,
  sortBy,
  offset,
  limit,
  reverse
})

// write
await library.configure(key, {isSaved, isHosting, visibility})
```

---

### LibraryDat

The values returned by library functions will fit the following object shape:

|Attribute|Type|Usage|
|-|-|-|
|key|`string`|The key of the dwebx|
|url|`string`|The url of the dwebx|
|author|`Object`|The dwebx that published the dwebx record (not necessarily the author of the dwebx)|
|&emsp;url|`string`||
|&emsp;title|`string`||
|&emsp;description|`string`||
|&emsp;type|`string`||
|&emsp;isOwner|`boolean`|Is the local user the owner of the author dwebx?|
|meta|`Object`|Information about the dwebx|
|&emsp;title|`string`||
|&emsp;description|`string`||
|&emsp;type|`string`||
|&emsp;mtime|`number`|The timestamp of the last observed change to the dwebx|
|&emsp;size|`number`|The local size of the dwebx in bytes|
|&emsp;author|`url`|The url of the author of this dwebx|
|&emsp;forkOf|`url`|The url of the dwebx this dwebx is forked from|
|&emsp;isOwner|`boolean`|Is the local user the owner of the dwebx?|
|isSaved|`boolean`|Has the local user saved the dwebx?|
|savedAt|`number`|The timestamp of when the dwebx was saved to the local user's library|
|isHosting|`boolean`|Is the local user hosting the dwebx?|
|visibility|`string`|The [visibility](/docs/common-fields#visibility) of the dwebx and its record|

---

### Notes

The canonical record of a saved dwebx is stored privately. If the visibility is "public" then a link-entry will also be added to the [public dvaults record](/dvaults).

Thumbnails of published dvaults should be published at `/.data/thumbs/` using the key as the filename.

---

### list(opts)

List dvaults by that are saved locally or published by authors.

|Param|Type|Default|Usage|
|-|-|-|-|
|opts|`Object`|||
|&emsp;authors|`string|string[]`||Filter by author URLs|
|&emsp;types|`string|string[]`||Filter by dwebx types|
|&emsp;keys|`string|string[]`||Filter by dwebx keys|
|&emsp;isSaved|`boolean`||Filter by: Has the local user saved the dwebx?|
|&emsp;isHosting|`boolean`||Filter by: Is the local user hosting the dwebx?|
|&emsp;visibility|`string`|`'all'`|Filter by this visibility. See [visibility](/docs/common-fields#visibility)|
|&emsp;forkOf|`string`||Filter by: Only forks of this URL|
|&emsp;isOwner|`boolean`||Filter by: Is the local user the owner of the dwebx?|
|&emsp;sortBy|`string`|`'topic'`|One of: `'topic'`|
|&emsp;offset|`number`|0||
|&emsp;limit|`number`|||
|&emsp;reverse|`boolean`|`false`||

|Returns|
|-|
|`Promise<LibraryDat[]>`|

---

### configure(key, opts)

Configure a dwebx in the local user's library.

|Param|Type|Default|Usage|
|-|-|-|-|
|key|`string`||DWebX key (required)|
|opts|`Object`|||
|&emsp;isSaved|`boolean`||Save the dwebx to the local user's library?|
|&emsp;isHosting|`boolean`||Host the dwebx using the local user's devices?|
|&emsp;[visibility](/docs/common-fields#visibility)|`string`||One of: `'public'`, `'unlisted'`, `'private'`|

|Returns|
|-|
|`Promise<void>`|

