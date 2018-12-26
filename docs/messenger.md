## Messenger

### View conversations
#### `https://www.minds.com/api/v2/messenger/conversations`
* Method: `GET`
* Params: `limit=:int`

* Response:

| Parameters | type | Description |
| --- |:---:|---:|
| `status` | string | Output:"success" |
| `converstions` | list | a list of the first 12 [conversations](#conversations) |
| `load-next` | int | Output: 12 |
| `load-previous` | int | -12 |

### Authenticate with messenger
#### `https://www.minds.com/api/v2/messenger/keys/unlock`
* Method: `POST`
* Params: `{password: ":msgpassword"}`
* Response: `{"status":"success"}`


### Conversations
