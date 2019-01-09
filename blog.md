# Blog

## Fetching blogs from a channel
### `https://www.minds.com/api/v1/blog/owner/:channel_guid?limit=12&offset=&rating=2`
* Method: `GET`
* Request Params:
    * `:channel_guid` - replace this with the guid or the username of a channel
    * `limit` - The ammount of blog posts loaded
    * `offset` - Is set when older blogs should be loaded
    * `rating` - If the blog is rated mature or not

* Response:

| Parameter | Type | Description |
| --- | :---: | ---: |
| `status` | string | Output: "success" |
| `entities` | list | Returns a list of multiple blog posts |
| `load-next` | string | Some encoded string which can be passed to `offset` to load earlier blog posts |

## Fetching a single blog post
### `https://www.minds.com/api/v1/blog/:blog_guid`
* Method: `GET`
* Request params
    * `:blog_guid` - replace this with the guid of the accociated blog

* Response

| Parameter | Type | Description |
| --- | :---: | ---: |
| `status` | string | Output: "success" |
| `blog` | dict | Returns [blog](#blog_object) object |

## Blog_object

| Parameter | Type | Description |
| --- | :---: | ---: |
| `type` | string | Output: "object" |
| `subtype` | string | Output: "blog" |
| `guid` | string | guid of the blog. <br> Output: "923022352788193280" |
| `owner_guid` | string | The guid of the channel, which created that blog post. <br> Output: "568132636652875781" |
| `container_guid` | string | Same as `owner_guid` |
| `access_id` | string | Output: "2" |
| `title` | string | The title of the blog post. Output: "Where is your castle? (Group Notifications) #MindsGaming #Op #OpenMinds" |
| `body` | string | The content of the blog encoded in xml/html? <br> Output: "<?xml encoding=\"utf-8\" ?><p><br></p><p>Minds has recently removed the group option for notifications. That's right it is no longer a notification on the system.<br></p><p>..." |
| `excerpt` | string | Same as `body` but with no html tags. Output: "Minds has recently removed the group option for notifications. That's right it is no longer a notification on the system..." |
| `slug` | string | Basically the `title` of the blog, but used to make human-readable urls. <br> Output: "where-is-your-castle-group-notifications-mindsgaming-op-open" |
| `perma_url` | string | A human-readable link to the blog post. Basically `https://www.minds.com/MindsGaming/blog/:slug`. Output: "https://www.minds.com/MindsGaming/blog/where-is-your-castle-group-notifications-mindsgaming-op-open-923022352788193280" |
| `has_header_bg` | bool | Output: `true` |
| `header_top` | string | Output: "0" |
| `time_created` | string | The time when this blog post has been created. <br> Output: "1545441677"|
| `time_updated` | string | The last time this blog has been edited. Has same value has `time_created` if not edited. <br> Output: "1545482051" |
| `last_updated` | string | Output: "1545482051" |
| `status` | string | Output: "" |
| `published` | bool | If the blog post is visible for everyone or not. <br> Output: `true` |
| `monetized` | bool | If the blog has been monetized. <br> Output: `false` |
| `license` | string | Under which license the channel has set this blog to. <br> Output: ""|
| `time_published` | string | The time of when this blog got published. <br> Output: "1545441677" |
| `categories` | list | An empty list |
| `custom_data` | dict | Output: `{"title": "","description": "","author": ""}` |
| `rating` | int | Output: `1` |
| `draft_access_id` | string | Output: "0" |
| `last_save` | string | Same as `time_updated` <br> Output: "1545482051" |
| `wire_threshold` | bool | The ammount of tokens, needed to be sent to view this blog post <br> Output: `false` |
| `paywall` | bool | If this blog post requires token payment for access. <br> Output: `false` |
| `mature` | bool | If this blog is rated mature or not <br> Output: `false` |
| `spam` | bool | If this blog post got flagged as spam <br> Output: `false` |
| `deleted` | bool | If this blog post is deleted <br> Output: `false` |
| `boost_rejection_reason` | int | Output: -1 |
| `ownerObj` | dict | Returns [channel]-data of the author |
| `tags` | list | accociated hashtags to this blog post. <br> Output: `[]` |
| `ownerObj` | dict | Returns [channel]-data of the author AGAIN |
| `description` | string | Same as `body` |
| `category` | string | Output: "" |
| `header_bg` | bool | Output: `true` |
| `thumbs:up:user_guids` | list | A list of guids from channels, which upvoted the blog |
| `thumbs:down:user_guids` | list | A list of guids from channels, which downvoted the blog |
| `thumbs:up:count` | int | The amount of upvotes. <br> Output: `67` |
| `thumbs:down:count` | int | The amount of downvotes. <br> Output: `0` |
| `reminds` | int | The amount of times this post has been reminded |
| `route` | string | The another url-path to the blog post. <br> Output: "MindsGaming/blog/where-is-your-castle-group-notifications-mindsgaming-op-open-923022352788193280" |
| `thumbnail_src` | string | A direct link the the banner image of the blog post. <br> Output: "https://cdn.minds.com/fs/v1/banners/923022352788193280/1545482051" |
