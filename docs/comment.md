## Comments/Posts

Writing posts in groups or from a timeline uses the same endpoit, but does differ by the request which needs to be sent

### Write a comment from the Newsfeed
#### ` GET /api/v1/newsfeed`
* Method: `POST`
* Authentication: required
* Request:

| Parameter | type | Description |
| --- |:---:| ---:|
| `message` | string | your post here |
| `wire_threshhold` | ? | specifies the ammount of tokens, a user needs to send to access that post. Output: 0 |
| `is_rich` | int | Shows if it has advanced formatting. Output: 0 |
| `title` | string | Output: "" |
| `description` | string| Output: "" |
| `thumbnail` | string | Output: "" |
| `url` | string | Output: "" |
| `attatchemt_guid` | ? | Output: null |
| `mature` | int | If the post is rated as mature or not. Output: 0 |
| `access_id` | int | Output: 2 |
| `tags` | list | hashtags included in the post |

* Response:
    
| Parameter | type | Description |
| --- |:---:| ---:|
| `status` | string | Output: "success" |
| `guid` | string | the id of the created post. You can take the guid and enter it like this `https://www.minds.com/newsfeed/:guid` |
| `activity` | dict | Gives out the [activity](#activity) of the post |

### Write a comment into a group

* Params:
    * dict: `{"message":"Your message here","wire_threshold":null,"is_rich":0,"title":"","description":"","thumbnail":"","url":"","attachment_guid":null,"mature":0,"container_guid":"864241400084602880","access_id":"864241400084602880","tags":[]}`
* Response:
    * json: `{"status":"success","guid":"923890509491490816","activity":{"guid":"923890509491490816","type":"activity","time_created":"1545648662","time_updated":"1545648662","container_guid":"864241400084602880","owner_guid":"618457429289480205","access_id":"864241400084602880","tags":[],"title":false,"blurb":false,"perma_url":false,"message":"Is this thing on?","ownerObj":{"guid":"618457429289480205","type":"user","subtype":false,"time_created":"1472827741","time_updated":false,"container_guid":"0","owner_guid":"0","site_guid":false,"access_id":"2","tags":[":hashtags"],"name":":screenname","username":":username","language":"en","icontime":"1541512228","legacy_guid":false,"featured_id":false,"banned":"no","website":"","briefdescription":"(\\ OwO \/)","dob":"","gender":"private","city":"","merchant":false,"boostProPlus":false,"fb":false,"mature":"0","monetized":"","signup_method":false,"social_profiles":[],"feature_flags":false,"programs":[],"plus":false,"hashtags":false,"verified":false,"founder":false,"disabled_boost":false,"boost_autorotate":false,"categories":["gaming","art","animals","technology","music"],"wire_rewards":null,"pinned_posts":["845689029699313664"],"is_mature":false,"mature_lock":false,"last_accepted_tos":"1536928774","opted_in_hashtags":"2","chat":true,"subscribed":false,"subscriber":false,"boost_rating":"2","rewards":true,"p2p_media_enabled":false,"eth_wallet":":ethwallet","rating":"1"},"containerObj":{"guid":"864241400084602880","type":"group","name":"Minds Group Testing","brief_description":"A group to test out Minds Group functions\n\n\nMinds Group Admins\nhttps:\/\/www.minds.com\/groups\/profile\/806941869062418432","icon_time":"1531430013","banner":"1531427931","banner_position":"0","membership":"2","moderated":"1","default_view":"0","featured":"0","featured_id":null,"tags":[],"boost_rejection_reason":"-1","mature":false,"rating":"1","videoChatDisabled":"1","owner_guid":"614198139255005203","members:count":"36","requests:count":"0","icontime":"1531430013","briefdescription":"A group to test out Minds Group functions\n\n\nMinds Group Admins\nhttps:\/\/www.minds.com\/groups\/profile\/806941869062418432","is:owner":false,"is:moderator":false,"is:member":true,"is:creator":false,"is:awaiting":false,"comments:count":"6"},"thumbnail_src":false,"remind_object":false,"entity_guid":false,"featured":false,"featured_guid":false,"custom_type":false,"custom_data":false,"thumbs:up:count":0,"thumbs:up:user_guids":[],"thumbs:down:count":0,"thumbs:down:user_guids":false,"p2p_boosted":false,"mature":false,"monetized":false,"paywall":false,"edited":false,"comments_enabled":true,"wire_totals":{"tokens":"0"},"boost_rejection_reason":-1,"pending":true,"rating":2,"comments:count":0,"impressions":0,"reminds":0,"wire_threshold":null}}`

### Write a comment under a post

* Params:
    * dict: `{"is_rich":0,"title":"","description":"","thumbnail":"","url":"","attachment_guid":null,"mature":0,"access_id":2,"comment":":message"}`
* Response:
    * json: `{"status":"success","comment":{"type":"comment","entity_guid":923884043321114624,"parent_guid":"923884043321114624","guid":"eyJfdHlwZSI6ImNvbW1lbnQiLCJlbnRpdHlfZ3VpZCI6IjkyMzg4NDA0MzMyMTExNDYyNCIsImd1aWQiOiI5MjM5ODUwOTkwMjQyNTcwMjQiLCJwYXJlbnRfZ3VpZCI6IjAifQ==","has_children":false,"owner_guid":"618457429289480205","container_guid":"618457429289480205","time_created":1545671214,"time_updated":1545671214,"access_id":2,"body":":message","attachments":[],"mature":false,"edited":false,"spam":false,"deleted":false,"_guid":"923985099024257024","luid":"eyJfdHlwZSI6ImNvbW1lbnQiLCJlbnRpdHlfZ3VpZCI6IjkyMzg4NDA0MzMyMTExNDYyNCIsImd1aWQiOiI5MjM5ODUwOTkwMjQyNTcwMjQiLCJwYXJlbnRfZ3VpZCI6IjAifQ==","ownerObj":{"guid":"618457429289480205","type":"user","subtype":false,"time_created":"1472827741","time_updated":false,"container_guid":"0","owner_guid":"0","site_guid":false,"access_id":"2","tags":[":hashtags"],"name":":displayname","username":":username","language":"en","icontime":"1541512228","legacy_guid":false,"featured_id":false,"banned":"no","website":"","briefdescription":"(\\ OwO \/)","dob":"","gender":"private","city":"","merchant":false,"boostProPlus":false,"fb":false,"mature":0,"monetized":"","signup_method":false,"social_profiles":[],"feature_flags":false,"programs":[],"plus":false,"hashtags":false,"verified":false,"founder":false,"disabled_boost":false,"boost_autorotate":false,"categories":["gaming","art","animals","technology","music"],"wire_rewards":null,"pinned_posts":["845689029699313664"],"is_mature":false,"mature_lock":false,"last_accepted_tos":1536928774,"opted_in_hashtags":2,"chat":true,"subscribed":false,"subscriber":false,"boost_rating":"2","rewards":true,"p2p_media_enabled":false,"eth_wallet":":ethwallet","rating":1},"description":":message"}}`

### Activity

| Parameter | type | Description |
| --- |:---:|---:|
| `guid` | string | [guid of the decribed post] |
| `type` | string | Output: "activity" |
| `time_created` | string | server time of when this post has been crated. Output: "1545830005" |
| `time_updated`| string | server time of when the post has last been edited |
| `container_guid` | string | The ID of which timeline that post is visible |
| `owner_guid`| string | ID of the creator of that post. Can be the same as `container_guid`|
| `access_id` | string| Output: "2" |
| `tags` | list | A collections of all hashtags, that are found in the body of the post |
| `title` | bool | Output: false |
| `blurb` | bool | Output: false |
| `perma_url` | bool | Output: false |
| `message` | string | The written content of the post. |
| `ownerObj` | dict | Returns all [user]-data of the author|
| `containerObj` | bool | Output: false |
| `thumbnail_src` | string | url source of the image, attatched to the post |
| `remind_object`| bool | Output: false |
| `entitiy_guid` | bool | Output: false |
| `featured` | bool | Output: false |
| `featured_guid` | bool | Output: false |
| `custom_type` | bool | Output: false |
| `custom_data` | bool | Output: false |   
| `thumbs:up:count`| int | The ammount of upvotes this post recieved |
| `thumbs:up:user_guids`| list | The list channel-ids, which have upvoted this post|
| `thumbs:down:count` | int | ammount of downvotes |
| `thumbs:down:user_guids` | bool | Output: false |
| `p2p_boosted` | bool | If this post has been p2p-boosted. Output: false |
| `mature` | bool | if true, then a censored bar covers the post by default (on the minds frontend)|
| `monetization` | bool | Output: false |
| `paywall` | bool | If the paywall is enabled, other users have to pay a specified ammount of tokens to view this post. Output: false|
| `edited` | bool | If this post has been edited or not |
| `comments_enable` | bool | if comments under this post are enabled or not |
| `wire_tokens` | dict | The ammount of tokens, which have been wired to this post. Output: `{"tokens": "0"}` |
| `boost_rejection_reason` | int | setting for which reason the post has been rejected to be boosted. The output is `-1`, most likely because I haven't even boosted it |
| `pending` | bool | status if this post is pending to be reviewd for boosting |
| `rating` | int | Output: 2 |
| `comments:count` | int| the ammount of comments under this post |
| `impressions` | int | The ammount of views, this post has recieved|
| `reminds` | int | The ammount of times, this post has been reminded|
| `wire_threshold`| ? | Output: null |
