# Videos

## List Videos from a user
### `/api/v1/entities/owner/videos/:username?limit=:int&offset=&rating=2`
* Method: `GET`
* Params:
    * `limit` - How specify how many posts get loaded at the same time
    * `offset` - The `:media_guid` from which the query should start
    * `rating`-  Probably if it's set to mature or not. If set to `2` it's sfw, but `3` is nsfw
* Response:

| Parameter | Type | Description |
| --- | :---: | ---: |
| `success` | string | Output: "success" |
| `entities` | list | Returns a list of multiple [entities](#entities) |
| `load-next` | string | The guid which can be appended to `offset` to load earlier posts |
| `load_previous` | string | The guid which can be appended to `offset` to load later posts |

## View data from a single video from the gallery
### `/api/v1/media/recommended/video/:channel_guid?current=:media_guid&next=&limit=6`
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

## View only the video
### `https://cdn-cinemr.minds.com/cinemr_com/:media_guid/:size`
* Method: `GET`
* Request Params:
    * `:media_guid` - replace this with the guid of the video
    * `:size`  - replace this with the desired image size:
        * `360.mp4` - Video output encoded in 320p
        * `720.mp4` - Video output encoded in 720p
        * `source` - original video file without file ending

## Entities

| Parameter | Type | Description |
| --- | :---: | ---: |
| `guid` | string | The guid of the video post |
| `type` | string | Output: "object" |
| `subtype` | string | Output: "video" |
| `time_created` | string | Servertime of when this post has been created |
| `time_updated` | string | Similar to `time_edited` but has a different value of when the post was last edited |
| `container_guid` | string | The guid of either a channel of a group which holds this post |
| `owner_guid` | string | The guid of the channel, which created this post. |
| `access_id` | string | Output: "0" |
| `title` | string | The discription of the video by the uploader. <br> Output: "#NYC #SubwayJams" |
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
| `cinemr_guid` | string | Same output as `guid` above |
| `license` | string | The license one has specified for this post |
| `mature` | bool | If this post is rated mature or not. <br> Output: `false` |
| `boost_rejection_reason` | int | Output: `-1` |
| `thumbnail_src` | string | The absolute url-path to the video thumbnail, which gets displayed. <br> Output: "https://cdn.minds.com/api/v1/media/thumbnails/826867867606671360/1522516662" |
| `src` | list | Gives out links of the video in two image qualities in form of a [list](#src)|
| `play:count` | int | The number of times, this video has been played |
| `description` | string | Output: "<?xml encoding=\"utf-8\" ?>\n" |
| `rating` | int | Output: `1` |

## src

| Parameter | Type | Description |
| --- | :---: | ---: |
| `360.mp4` | string | A direct link to the video in 360p. <br> Output: "https://cdn-cinemr.minds.com/cinemr_com/826867867606671360/360.mp4" |
| `720.mp4` | string | A direct link to the video in 720p. <br> Output: "https://cdn-cinemr.minds.com/cinemr_com/826867867606671360/720.mp4" |
