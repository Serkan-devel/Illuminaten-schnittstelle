# Messenger

One of the seeling points of 'Minds' is that their messenger is encrypted, hence their name "encrypted chat".
Considering that almost all messenger encryption happends on the server-side, an admin or a hacker only needs to view all plaintext authentication requests, or tamper with the encryption keys.
Users of the messenger won't notice if anything got tampered or spyed on but it's still enough to give them a false-sense of security.

Before using the messenger, you first have to [authenticate](auth.html#authenticate-with-messenger) to it seperately.

## View conversations
### `https://www.minds.com/api/v2/messenger/conversations`
* Method: `GET`
* Params: `limit=:int`

* Response:

| Parameter | type | Description |
| --- |:---:|---:|
| `status` | string | Output:"success" |
| `converstions` | list | a list of the first 12 [conversations](#conversations) |
| `load-next` | int | Output: 12 |
| `load-previous` | int | Output: -12 |

## View chat timeline
### `https://www.minds.com/api/v2/messenger/conversations/{your guid}:{other guid}?limit=8&offset={message guid}&finish=`
* Method: `GET`
* Params: `limit=8&offset=&finish=`
* Response:

| Parameter | type | Description |
| --- |:---:|---:|
| `status` | string | Output: "success" |
| `guid` | string | The guid of you and the id of the one, you're talking to. <br> Output: "618457429289480205:661345766295478287"|
| `type` | string | Output:"messenger" |
| `subtype` | string | Output: "consversation" |
| `unread` | int | Output: 0|
| `online` | bool | false |
| `ts` | int | Timestamp. Output: "1541346828" |
| `participants`| list | basically, the user-object of the one, your're contacting |
| `name` | string | @-name of the other user |
| `username` | string | Displayname of the other user |
| `socketRoomName` | string | basically `guid` but with `conversation:` prepended to it. <br> "conversation:618457429289480205:661345766295478287" |
| `blocked` | string | if you blocked that user |
| `unavailable` | bool | Output: false |
| `messages` | list | A chain of [messages](#messages) between you and the other user |
| `load-next` | string | guid of the next messages |
| `load-previos` | string | guid of the previous messages |
| `publickeys` | dict | A dict of your public key, the public key of the other user and the public key of the room. <br> `{[your guid]:[public key],[his/her guid]:[public key],[(your guid):(his/her guid)]:[public key]}` |

## Comment in Chat
* Method: `GET`
* Request:

| Parameter | type | Description |
| --- |:---:|---:|
| `message` | string | the message that you send |
| `encrypt` | bool | Output: `true` |
| `tabID` | string | Output: "6yxhy" |

* Response:
    Same as [messages](#messages) but with only one difference

| Parameter | type | Description |
| --- |:---:|---:|
| `messages` | dict | A dictionary with both guids of you and the reciever, but with encryption keys attatched to it. <br> Example: `"messages": {[your guid]:[encryption key],[reciever guid]:[encryption key]}`|


## Conversations

| Parameter | type | Description |
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


## Messages

| Parameter | type | Description |
| --- |:---:|---:|
| `guid` | string | the guid of this message block |
| `friendly_ts` | ? | null |
| `messages` | string | the content of the message, displayed |
| `messages` | dict | a guid and the message above. <br> Example: `"messages": {"018454429285497205": "textual content here"}` |
| `type` | string | Output:"object" |
| `subtype` | string | Output:"message" |
| `owner_guid` | ? | Output: null |
| `owner` | dict | the user information of the author of that message|
| `time_created` | string | servertime when this message has been made. <br> Example: "1542346933" |
| `ownerObj` | dict | same as owner but the `guid`-field at the top has an empty string |
