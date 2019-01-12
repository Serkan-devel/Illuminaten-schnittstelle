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

