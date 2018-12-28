## Timeline


### View user timeline
#### `https://www.minds.com/api/v1/newsfeed/personal/{user guid}?limit=12&offset=&pinned={post guid}`
* Method: `GET`
* Request URL Params:
    * `limit`: how many posts are recieved at a time
    * `offset` : from which guid the [activity](#activity) should start
    * `pinned` : guid of the pinned post
* Response:

| Parameter | Type | Description |
| --- | :---: | ---: |
| `success` | string | Output: "success" |
| `load-previous` | string | the activity guid, which loads previous posts and can be passed via the `offset` parameter |
| `pinned` | list | The [activity](#activity) of all pinned posts |
| `activity` | list | The [activity](#activity) of the timeline |
| `load-next` | string | The guid, leading to later posts|


### Activity

Activity is simply just an array of posts
