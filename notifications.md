# Notifications

## Fetching notifications
### `https://www.minds.com/api/v1/notifications/:scope?limit=24&offset=`
* Method: `GET`
* Authentication: Required
* Params: 
    * `:scope` - Notification scoping
        * `all` - fetch all notifications
        * `tags` - fetch notifications you are tagged on
        * `comments` - fetch notifications of comment threads, you are following
        * `groups` - fetch notifications of group interactions
        * `votes` - fetch notifications containing voting of your posts
    * `limit` - pagination limit
    * `offset` - pagination offset
* Response:  

| Parameter | type | Description |
| --- |:---:|---:|
| `status` | string | Output: "success" |
| `notifications` | list | a list of Notifications|
| `load-next` | string | Pagaination offset value. Can be passed to `offset` |

## Notification object

## Notification comments

| Parameter | type | Description |
| --- |:---:|---:|
| `guid` | string | Notification guid. <br> Output: "514d0f48-7b44-43a8-9af2-fbc2c1772eee" |
| `uuid` | string | Same as `guid` |
| `description` | string | The comment which has been posted |
| `filter` | string | Output: "comment" |
| `entityObj` (TODO) | dict | Might either contain a [video object], an [image object], a [post object] or a [blog object] |
| `from_guid` | int | The `:channel_guid` which created that comment |
| `fromObj` | dict | The [Channel object] of the commenter |
| `to` | dict | Your [Channel object] |
| `params` (TODO) | dict | Contains `description` again |
| `time_created` | int | Servertime of when this comment was made |
| `entity` | dict | Same as `entityObj` |
| `from` | dict | Same as `fromObj` |
| `owner` | dict | Also same as `fromObj` |


