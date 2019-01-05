# Media

## List images from a user
## `/api/v1/entities/owner/images/:username?limit=:int&offset=&rating=2`
* Method: `GET`
* Params:
    * `limit` - How specify how many posts get loaded at the same time
    * `offset` - The `:media_guid` from which the query should start
    * `rating`- ? Probably if it's set to mature or not
* Response:
    * json: ``

## View data from a single image post
### `/api/v1/media/recommended/image/:channel_guid?current=:media_guid&next=&limit=6`
* Method: `GET`
* Request params:
    * `:channel_guid` - The channel from which the media has been created
    * `current` - The current image shown, specified with `:media_guid`
    * `next` - pobably the next image post to be shown. Sometimes it's empty
    * `limit` - The images shown at the sidebar of the page. 
* Response:

| Parameter | Type | Description |
| --- | :---: | ---: |
| `status` | string | Output: "success" |
| `entities` | list | A list of multiple [Entities](#entities) |

## View only the image
### `https://www.minds.com/api/v1/media/thumbnails/:media_guid/:size`
* Method: `GET`
* Request Params:
    * `:media_guid` - replace this with the guid of the image
    * `size`  - replace this with the desired image size:
        * `large`
        * `xlarge`
        * `small`
        * `master`

## Entities

| Parameter | Type | Description |
| --- | :---: | ---: |
| `guid` | string | The guid of the media post |
| `type` | string | Output: "Object" |
| `subtype` | string | Output: "image" |
| `time_created` | string | Servertime of when this post has been created |
| `time_updated` | string | Similar to `time_edited` but has a different value of when the post was last edited |
| `container_guid` | string | The guid of either a channel of a group which holds this post |
| `owner_-guid` | string | The guid of the channel, which created this post. |
| `access_id` | string | Output: "0" |
| `title` | string | Output: "" |
| `featured` | bool | Output: `false` |
| `featured_id` | bool | Output: `false` |
| `ownerObj` | dict | Returns all info of the channel, which created this post |
| `category` | bool | Output: `false` |
| `comments:count` | bool | Output: `false` |
| `thumbs:up:count`| int | How many times, this post has been upvoted. <br> Output: `79` |
| `thumbs:up:user_guids` | list | A list of all guids from channels which have upvoted this post |
| `thumbs:down:count` | int | How many times this post has been downvoted. <br> Output: `0` |
| `thumbs:down:user_guids` | bool | Output: `false` |
| `flags` | dict | Output: `{"mature": false}` |
| `wire_threshold` | string | The minimum ammount of tokens, one has to wire to view this post. <br> Output: "0" |
| `thumbnail` | bool | Output: `false` |
| `cinemr_guid` | bool | Output: `false` |
| `license` | string | The license one has specified for this post |
| `mature` | bool | If this post is rated mature or not. <br> Output: `false` |
| `boost_rejection_reason` | int | Output: `-1` |
| `rating` | int | Output: `2` |
| `width` | int | The width of the image. <br> Output: `750` |
| `height` | int | The height of the image. <br> Output: `746` |
| `gif` | bool | If this image is a gif or not. <br> Output: `false` |
| `thumbnail_src` | string | The absolute url-path to the image, which gets displayed. <br> Output: `"https://www.minds.com/api/v1/media/thumbnails/926522707021164544/large"` |
| `description` | ? | Output: `null` |

