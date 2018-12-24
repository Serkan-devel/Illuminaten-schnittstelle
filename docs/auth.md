## Authentication

Current authentication-method is only [HTTP Basic Authentication](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Authorization).

Minds staff still developing on OAuth-support to make this process more secure.

### `/api/v1/authenticate`
#### Login to Minds.com with your username and password
* Method: `POST`
* Params:
    * dict: `{username: ":username", password: ":password"}`
* Response:
    `{success: "success",...}`
* Note: You need to pass xsrf-tokens and cookies on the http-header

### `/api/v1/newsfeed`
#### Write a comment from the Newsfeed
* Method: `POST`
* Params:
    * dict: `{"message":"Your message here","wire_threshold":null,"is_rich":0,"title":"","description":"","thumbnail":"","url":"","attachment_guid":null,"mature":0,"access_id":2,"tags":[]}`
* Response:
    * json: `{"status":"success","guid":"923880589957693440","activity":{"guid":"923880589957693440","type":"activity","time_created":"1545646297","time_updated":"1545646297","container_guid":"618457429289480205","owner_guid":"618457429289480205","access_id":"2","tags":[],"title":false,"blurb":false,"perma_url":false,"message":"UwU","ownerObj":{"guid":"618457429289480205","type":"user","subtype":false,"time_created":"1472827741","time_updated":false,"container_guid":"0","owner_guid":"0","site_guid":false,"access_id":"2","tags":["freemistressmei"],"name":"SerkanDevel","username":"SerkanDevel","language":"en","icontime":"1541512228","legacy_guid":false,"featured_id":false,"banned":"no","website":"","briefdescription":"(\\ OwO \/)","dob":"","gender":"private","city":"","merchant":bool,"boostProPlus":bool,"fb":false,"mature":"0","monetized":"","signup_method":false,"social_profiles":[],"feature_flags":false,"programs":[],"plus":false,"hashtags":false,"verified":false,"founder":false,"disabled_boost":bool,"boost_autorotate":bool,"categories":["gaming","art","animals","technology","music"],"wire_rewards":null,"pinned_posts":[":guid"],"is_mature":bool,"mature_lock":bool,"last_accepted_tos":"1536928774","opted_in_hashtags":"2","chat":true,"subscribed":false,"subscriber":false,"boost_rating":"2","rewards":true,"p2p_media_enabled":false,"eth_wallet":":ethwallet","rating":"1"},"containerObj":false,"thumbnail_src":false,"remind_object":false,"entity_guid":false,"featured":false,"featured_guid":false,"custom_type":false,"custom_data":false,"thumbs:up:count":0,"thumbs:up:user_guids":[],"thumbs:down:count":0,"thumbs:down:user_guids":false,"p2p_boosted":false,"mature":false,"monetized":false,"paywall":false,"edited":false,"comments_enabled":true,"wire_totals":{"tokens":"0"},"boost_rejection_reason":-1,"pending":false,"rating":2,"comments:count":0,"impressions":0,"reminds":0,"wire_threshold":null}}`
