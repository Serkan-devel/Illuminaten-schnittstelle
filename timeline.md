# Timeline


## View channel timeline
### `https://www.minds.com/api/v1/newsfeed/personal/:user_guid?limit=12&offset=&pinned=:post_guid`
## View group timeline
### `https://www.minds.com/api/v1/newsfeed/container/:group_guid?limit=12&offset=`
## View a single timeline post
### `https://www.minds.com/api/v1/newsfeed/single/:post_guid`
* Method: `GET`
* Request URL Params:
    * `limit`: how many posts are recieved at a time. Default is `12`
    * `offset` : from which guid the [activity](#activity) should start. Default is ``
    * `pinned` : The post of a guid, which has been pinned (`:post_guid`) 
* Response:

| Parameter | Type | Description |
| --- | :---: | ---: |
| `success` | string | Output: "success" |
| `load-previous` | string | the activity guid, which loads previous posts and can be passed via the `offset` parameter |
| `pinned` | list | The [activity](#activity) of all pinned posts |
| `activity` | list | The [activity](#activity) of the timeline |
| `load-next` | string | The guid, leading to later posts|


## Activity

Activity is simply just an array of posts
