# Comments

## Writing a comment
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

## Comment

| Parameter | type | Description |
| --- |:---:|---:|
| `type` | string | Output:"comment" |
| `entity_guid` | int | The guid of the comment itself? |
| `parent_guid` | string | The guid of the post, one has commented under |
| `guid` | string | A base64-encoded json string [check decoded output](#comment_guid) |
| `has_children` | bool | Output: `false` |
| `owner_guid` | string | The guid of the channel who created this comment |
| `container_guid` | string | Same as `owner_guid` |
| `time_created` | int | The servertime of when this comment has been posted. <br> Output: 1546701454 |
| `time_edited` | int | The last time this has been edited. If this comment has never been change, it's the same as `time_created` |
| `access_id` | int | Output: 2 |
| `body` | string | The actual content of the comment, which has been written |
| `attatchments` | list | Either an empty list or an object with [attachments](#attachments) |
| `mature` | bool | If this comment is rated mature or not. <br> Output: `false` |
| `edited` | bool | If this comment has been edited or not. <br> Output: `false` |
| `spam` | bool | If this comment has been marked as spam or not. <br> Output: `false` |
| `deleted` | bool | If this comment has been deleted or not? <br> Output: `false` |
| `_guid` | string | Output: "928306239371825152" |
| `luid` | string | A base64-encoded json string which has the same structure as [Comment_guid](#comment_guid) |
| `ownerObj` | dict | Gives out all public data of the user who created this comment |
| `description` | string | same as `body` |
| `thumbs:up:user_guids` | list | A list of `:channel_guid`s which upvoted this comment |
| `thumbs:up:count` | int | The ammount of upvotes |
| `thumbs:down:user_guids` | list | A list of `:channel_guid`s which downvoted this comment |
| `thumbs:down:count` | int | The ammount of downvotes on this comment |

## Comment_guid

| Parameter | type | Description |
| --- |:---:|---:|
| `_type` | string | Output: "comment" |
| `entity_guid` | string | The guid of the post which has been commented on |
| `guid` | string | The same guid as seen on `_guid` at [Comment](#comment) |
| `parent_guid` | string | Output: "0" |

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
| `videoChatDisabled` | string | Minds Video Calling, coming soon™ <br> Output: "1" |
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
### `https://www.minds.com/api/v1/thumbs/[base64-encoded string]/{up or down}`
* Method: `PUT`
* Request: 

| Key | Value |
| --- | --- |
| `_type` | "comment" |
| `entity_guid`| "924651117277278208" |
| `parent_guid` | "0" |

* Response: `{"status":"success"}`
