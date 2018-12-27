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
| `load-previous` | int | Output: -12 |

### View chat timeline
#### `https://www.minds.com/api/v2/messenger/conversations/{your guid}:{other guid}?limit=8&offset=&finish=`
* Method: `GET`
* Params: `limit=8&offset=&finish=`
* Response:

| Parameters | type | Description |
| --- |:---:|---:|
| `status` | string | Output: "success" |

### Authenticate with messenger
#### `https://www.minds.com/api/v2/messenger/keys/unlock`
* Method: `POST`
* Params: `{password: ":msgpassword"}`
* Response: `{"status":"success"}`


### Conversations

| Parameters | type | Description |
| --- |:---:|---:|
| `guid` | string | Your userID and the id of the one you have in contact, is being displayed here.<br> The Format of it looks a little like this `{your guid}:{guid of the other user}`. <br> Output: "618457429289480205:661345766295478287" |
| `type`| string | Output: "messenger" |
| `subtype` | string| Output: "conversation" |
| `unread` | int | Unread messages from that conversation. <br> Output: 0 |
| `online` | bool | returns true if the user is online |
| `ts` | int | Output: 1541346828 |
| `participants` | list | outputs userdata from the other user (including settings and birthdate) |
| `name` | string | displayname of the other user |
| `username` | string | @-name of the other user |
| `socketRoomName` | string| basically `guid` but with `conversation:` prepended to it. <br> Output: "conversation:618457429289480205:661345766295478287" |
| `subscribed` | bool | Is the other user subscribe to you |
| `subscriber` | bool | Are you subscribed to that user? |
