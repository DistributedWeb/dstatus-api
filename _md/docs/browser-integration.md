## Browser integration

[DBrowserX Browser 0.9](https://dbrowser.com) implements Unwalled.Garden as part of the browser. It supports a high-level API which is loaded from the [dwebx://unwalled.garden](dwebx://unwalled.garden) dwebx. These APIs wrap the DWebX filesystem and dBrowser's internal indexes.

```js
import {statuses, follows, reactions, comments} from 'dwebx://unwalled.garden/index.js'
await follows.add('dwebx://dbrowser.com')
var feed = await statuses.list({reverse: true, limit: 10})
var status = await statuses.add('Hello, world!')
await comments.add(status.url, 'Great post by me!')
await reactions.add(status.url, 'like')
```

The browser automatically creates a personal dwebx for the user on first load. The personal site acts as the user profile and is where the user's content is published.

```js
import {profiles} from 'dwebx://unwalled.garden/index.js'
var me = await profiles.me()
me.url         // 'dwebx://12cd..ff'
me.title       // 'Bob'
me.description // 'A hacker'
```

DBrowserX will track its APIs with the latest Unwalled.Garden standards. More implementations of the APIs will be created as the network matures.