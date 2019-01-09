# Search

## Normal search
### `https://www.minds.com/api/v2/search/top?q=:query&container=&limit=12&rating=3&offset=&sort=`
* Method: `POST`
* Request Params:
    * `q` - The specified search `:query`
    * `container`
    * `limit` - The ammount of posts loaded at one request
    * `offset` - To load earlier activities
    * `sort`

* Response

| Parameter | Type | Description |
| --- | :---: | ---: |
| `status` | string | Output: "success" |
| `entities` | dict | A dictionary, containing posts, users and groups |
| `load-next` | int | A number to be placed in `offset` to load earlier posts |

