## Follows API

Follows are subscriptions to sites. Following a site causes the user to download and see their content.

---

```js
import {follows} from 'dwebx://unwalled.garden/index.js'

// read
await follows.list({
  authors,
  topics,
  visibility,
  sortBy,
  offset,
  limit,
  reverse
})
await follows.get(author, topic)

// write
await follows.add(topic, {visibility})
await follows.edit(topic, {visibility})
await follows.remove(topic)
```

---

### Follow

The values returned by follow functions will fit the following object shape:

|Attribute|Type|Usage|
|-|-|-|
|author|`Object`|The site doing the following|
|&emsp;url|`string`||
|&emsp;title|`string`||
|&emsp;description|`string`||
|&emsp;type|`string`||
|topic|`Object`|The site being followed|
|&emsp;url|`string`||
|&emsp;title|`string`||
|&emsp;description|`string`||
|&emsp;type|`string`||
|visibility|`string`|The [visibility](/docs/common-fields#visibility) of the "follow" record|

---

### list(opts)

List follows by authors and/or topics.

|Param|Type|Default|Usage|
|-|-|-|-|
|opts|`Object`|||
|&emsp;authors|`string|string[]`||Filter by author URLs|
|&emsp;topics|`string|string[]`||Filter by topic URLs|
|&emsp;visibility|`string`|`'all'`|Filter by this visibility. See [visibility](/docs/common-fields#visibility)|
|&emsp;sortBy|`string`|`'topic'`|One of: `'topic'`|
|&emsp;offset|`number`|0||
|&emsp;limit|`number`|||
|&emsp;reverse|`boolean`|`false`||

|Returns|
|-|
|`Promise<Follow[]>`|

---

### get(author, topic)

Get a follow by author and topic.

|Param|Type|Default|Usage|
|-|-|-|-|
|author|`string`||Site URL (required)|
|topic|`string`||Site URL (required)|

|Returns|
|-|
|`Promise<Follow>`|

---

### add(topic, opts)

Add a follow to the current user's site.

|Param|Type|Default|Usage|
|-|-|-|-|
|topic|`string`||Site URL (required)|
|opts|`Object`|||
|&emsp;[visibility](/docs/common-fields#visibility)|`string`|`'public'`|One of: `'public'`, `'private'`|

|Returns|
|-|
|`Promise<void>`|

---

### edit(topic, opts)

Edit a follow on the current user's site.

|Param|Type|Default|Usage|
|-|-|-|-|
|topic|`string`||Site URL (required)|
|opts|`Object`|||
|&emsp;[visibility](/docs/common-fields#visibility)|`string`|`'public'`|One of: `'public'`, `'private'`|

|Returns|
|-|
|`Promise<void>`|

---

### remove(topic)

Remove a follow from the current user's site.

|Param|Type|Default|Usage|
|-|-|-|-|
|topic|`string`||Site URL (required)|

|Returns|
|-|
|`Promise<void>`|