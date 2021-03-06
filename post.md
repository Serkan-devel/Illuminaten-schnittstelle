# Posts

Writing posts in groups or from a timeline uses the same endpoit, but does differ by the request which needs to be sent

## Writing a Post
### `/api/v1/newsfeed`
* Method: `POST`
* Authentication: required
* Request:

| Parameter | type | Description |
| --- |:---:| ---:|
| `message` | string | your post here |
| `wire_threshhold` | ? | specifies the ammount of tokens, a user needs to send to access that post. Output: 0 |
| `is_rich` | int | Shows if it has advanced formatting. Output: 0 |
| `title` | string | Output: "" |
| `description` | string| Output: "" |
| `thumbnail` | string | Output: "" |
| `url` | string | Output: "" |
| `attatchemt_guid` | ? | Output: null |
| `mature` | int | If the post is rated as mature or not. Output: 0 |
| (optional) `container_guid` | string | This field only exists if you post into a group and holds the guid of it. |
| `access_id` | int/string | Might contain the guid of a group, otherwise it's 2 |
| `tags` | list | hashtags included in the post |

* Response:

| Parameter | type | Description |
| --- |:---:| ---:|
| `status` | string | Output: "success" |
| `guid` | string | ID of the post. You can vist this post like this `https://www.minds.com/newsfeed/:guid`. Output: "924651117277278208" |
| `activity` | dict | returns the [activity object](#activity) of the post |

## Writing a comment under a Post
### `https://www.minds.com/api/v1/comments/:guid`
* Method: `POST`
* Params:
    * `guid` - the guid of a post, blog, video or image
* Request

| Parameter | type | Description |
| --- |:---:| ---:|
| `is_rich` | int | If rich text is enabled. <br> Output: `0` |
| `title` | string | The title of a comment? <br> Oututp: "" |
| `description` | string | Output: "" |
| `thumbnail` | string | Output: "" |
| `attachment_guid` | ? | Output: `null` |
| `mature` | int | If the comment is rated mature or not. <br> Output: `0` |
| `access_id` | int | Output: `2` |
| `comment` | string | The actuall comment, which gets displayed |

* Response

| Parameter | type | Description |
| --- |:---:| ---:|
| `status` | string | Output: "success" |
| `comment` | dict | Dictionary of [Comment](#comment) |

## Loading comments
### `https://www.minds.com/api/v1/comments/:post_guid?limit=5&offset=&reversed=false`
* Method: `GET`
* Request params
    * `:post_guid` - replace this with the guid of a post,blog post,video or image
    * `limit` - the ammount of comments that are loaded
    * `offset` - If `load-earlier` gets passed it will load earlier comments from that thread respectively
    * `reversed` - if comments are loaded in reversed order. Set to `false` by default
* Response:

| Parameter | type | Description |
| --- |:---:| ---:|
| `status` | string | Output: "success" |
| `comments` | list | Holds an object of [comments](#comment) |
| `load-previous` | string | An encoded string which can be passed to `offset` to load earlier comments |
| `socketRoomName` | string | Basically it's `comments::channel_guid` |

## Activity

| Parameter | type | Description |
| --- |:---:|---:|
| `guid` | string | [guid of the decribed post] |
| `type` | string | Output: "activity" |
| `time_created` | string | server time of when this post has been crated. Output: "1545830005" |
| `time_updated`| string | server time of when the post has last been edited |
| `container_guid` | string | Either the guid of a channel or the guid of a group, on which this is posted |
| `owner_guid`| string | ID of the creator of that post. Can be the same as `container_guid` if not posted into a group |
| `access_id` | string | Output: "2" |
| `tags` | list | A collections of all hashtags, that are found in the body of the post |
| `title` | bool | Output: false |
| `blurb` | bool | Output: false |
| `perma_url` | bool | Output: false |
| `message` | string | The written content of the post. |
| `ownerObj` | dict | Returns all [user]-data of the author|
| `containerObj` | bool/dict | Either the [object of a group](#containerobj) or false |
| `thumbnail_src` | string | url source of the image, attatched to the post |
| `remind_object`| bool | Output: false |
| `entitiy_guid` | bool | Output: false |
| `featured` | bool | Output: false |
| `featured_guid` | bool | Output: false |
| `custom_type` | bool | Output: false |
| `custom_data` | bool | Output: false |   
| `thumbs:up:count`| int | The ammount of upvotes this post recieved |
| `thumbs:up:user_guids`| list | The list channel-ids, which have upvoted this post|
| `thumbs:down:count` | int | ammount of downvotes |
| `thumbs:down:user_guids` | bool | Output: false |
| `p2p_boosted` | bool | If this post has been p2p-boosted. Output: false |
| `mature` | bool | if true, then a censored bar covers the post by default (on the minds frontend)|
| `monetization` | bool | Output: false |
| `paywall` | bool | If the paywall is enabled, other users have to pay a specified ammount of tokens to view this post. Output: false|
| `edited` | bool | If this post has been edited or not |
| `comments_enable` | bool | if comments under this post are enabled or not |
| `wire_tokens` | dict | The ammount of tokens, which have been wired to this post. Output: `{"tokens": "0"}` |
| `boost_rejection_reason` | int | setting for which reason the post has been rejected to be boosted. The output is `-1`, most likely because I haven't even boosted it |
| `pending` | bool | status if this post is pending to be reviewd for boosting |
| `rating` | int | Output: 2 |
| `comments:count` | int| the ammount of comments under this post |
| `impressions` | int | The ammount of views, this post has recieved|
| `reminds` | int | The ammount of times, this post has been reminded|
| `wire_threshold`| ? | Output: null |


## containerObj

| Parameter | type | Description |
| --- |:---:|---:|
| `guid` | string | The guid of a group |
| `type` | string | Output: "group" |
| `name` | string | The name of the group |
| `brief_description` | string | The description of a group |
| `icon_time` | string | Output: "1534475237"|
| `banner` | string | Output: "1534475239" |
| `banner_position` | string | Output: "0" |
| `membership` | string | Output: "2" |
| `moderated` | string | Output: "0" |
| `default_view` | string | Output: "0" |
| `featured` | string | Output: "0" |
| `featured_id` | ? | Output: `null` |
| `tags` | list | A list of hashtags, which are set by the group admins |
| `boost_rejection_reason` | string | Output: "-1" |
| `mature` | bool | false |
| `rating` | string | Output: "1" |
| `videoChatDisabled` | string | Minds Gatherings, coming soon™ <br> Output: "1" |
| `owner_guid` | string | The guid of the channel, which created that group |
| `members:count` | string | The ammount of group members. <br> Output: "83" |
| `requests:count` | string | The ammount of channels, requesting membership <br> Output: "0" |
| `icontime` | string | Output: "1534475237" |
| `briefdescription` | string | Exactly the same as `brief_description` |
| `is:owner` | bool | Output: `false` |
| `is:moderator` | bool | Output: `false` |
| `is:member` | bool | Output: `true` |
| `is:creator` | bool | Output: `false` |
| `is:awaiting` | bool | At some groups, mods have to manually approve or denie posts to be viewable on the timeline <br>Output: `false` |
| `comments:count` | bool | The ammount of comments under the post. <br> Output: "0" |

## attachments

| Parameter | type | Description |
| --- |:---:|---:|
| `custom_type` | string | Output: "image" |
| `custom_data` | string | Returns [image](attachments_image) |
| `attachment_guid` | string | The guid of the attachment |

## attachments_image

| Parameter | type | Description |
| --- |:---:|---:|
| `guid` | dict | The guid of the attached image. <br> Output: "930127204450033664" |
| `container_guid` | string | The `:channel_guid` of the author, who created it |
| `src` | string | A direct link to the image `https://www.minds.com/fs/v1/thumbnail/:media_guid` |
| `href` | string | Similar to `src` but with a different url path which the user gets redirected to when clicked <br> `https://www.minds.com/media/:channel_guid/:media_guid`|
| `mature` | bool | If the attatchment is rated mature or not |
| `width` | int | The width of the attached image |
| `height` | int | The height of the attached image |

## Up/downvotes
### `https://www.minds.com/api/v1/thumbs/:post_guid/:vote`
* Method: `PUT`
* Request Params:
    * `:post_guid` - The guid which one wants to vote
    * `:vote` - Replace this with either `up` or `down` for voting 
