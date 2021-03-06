## How does Unwalled.Garden work?

Unwalled.Garden is a kind of "Souped up [RSS](https://en.wikipedia.org/wiki/RSS)." Every user has a website, they publish their content as files, and they subscribe to each others' sites.

While RSS was primarily for blogging, Unwalled.Garden includes data types for many kinds of use-cases. These data types are spread across many JSON files which have pre-defined schemas.

The schemas are simple, obvious, and syntax-free. A "status" record looks like this:

```json
{
  "type": "unwalled.garden/status",
  "body": "Hello, world!",
  "createdAt": "2019-05-21T21:27:45.471Z"
}
```

We identify the types using URLs such as:

 - [unwalled.garden/status](/status)
 - [unwalled.garden/comment](/comment)
 - [unwalled.garden/reaction](/reaction)
 - [unwalled.garden/person](/person)
 - etc

All files are placed at predefined paths. An example site might look like this:

|URL|Type|
|-|-|
|`dwebx://bob.com`|[Person](/person)|
|`dwebx://bob.com/.data`|[Data directory](/dir/data)
|`dwebx://bob.com/.data/statuses/hello.json`|[Status](/status)
|`dwebx://bob.com/.data/reactions/1.json`|[Reaction](/reaction)
|`dwebx://bob.com/.data/comments/1.json`|[Comment](/comment)

This site identifies as a [Person](/person) and it includes a [Status](/status), [Reaction](/reaction), and [Comment](/comment). A reader will crawl the website looking for these files to sync into its local database.

Unwalled.Garden is built for the [DWebX protocol](https://dwebx.foundation). Read an [introduction primer here](./dwebx-primer).