## Channels

### User


| Parameter | Type | Description |
| --- | :---: | ---: |
| `guid` | string | unique ID, associated with the account. Example: "618457429289480205" |
| `type` | string | Output: "user" |
| `time_created` | string | Output:"1472827741" |
| `time_updated` | bool | . |
| `container_guid` | string | Output: "0" |
| `owner_guid` | string | Output:"0" |
| `site_guid` | bool | . |
| `access_id` | string | Output:"2" |
| `tags` | list | A list of all hashtags, one has tagged on the bio. Example: "openminds" |
| `name` | string | The displayname, which the user can change |
| `username` | string | `@`-name, which can't be changed |
| `language` | string | language setting. Example: "en" |
| `icontime` | string | Output:"1541512228" |
| `legacy_guid` | bool | Output: `false` |
| `featured_id` | bool | Output: `false` |
| `banned` | string | If the channel is banned or not. Output: "no" |
| `website` | string | . |
| `briefdescription` | string | The text, displayed within the user bio |
| `dob` | string | date of birth |
| `gender` | string | "male","female","private" |
| `city` | string | . |
| `merchant` | bool | Output: `false` |
| `boostProPlus` | bool | Output: `false` |
| `fb` | bool | If you have a facebook account linked to it. Output: `false` |
| `mature` | int | Output: 0 |
| `monetized` | string | Output: "" |
| `signup_method` | bool | Output: `false` |
| `social_profiles` | list | A list of all social profiles, linked within the bio |
| `feature_flags` | bool | Output: `false` |
| `programs` | list | Output: "" |
| `plus` | bool | If the channel has minds plus enabled. Output:`false` |
| `hashtags` | bool | Output: `false` |
| `verified` | bool | Output: `false` |
| `founder` | bool | Users, who have sponsored minds.com on the [2017 Wefunder Campaign](https://wefunder.com/minds) have this |
| `disabled_boost` | bool | People with minds plus can opt-out of boosts from their feed |
| `boost_autorotate` | bool | If this is set to `true`, then the first boosted post always switches. This it by default `true` |
| `categories` | list | user preferences, responsible for what things mostly show up in the newsfeed |
| `wire_rewards` | | Output: `null` |
| `pinned_posts` | list | The user can pin posts to the top of their channel |
| `is_mature` | bool | Output: false |
| `mature_lock` | bool | usually channels with a mature rating, have every post rated mature by default. Output: false |
| `last_accepted_tos` | int | The last Terms-of-service, accepted by the user. Output:1536928774 |
| `opted_in_hashtags` | int |hashtags, one has selected for search |
| `chat` | bool | if the user have messenger enabled |
| `boost_rating` | int | Output:2 |
| `rewards` | bool | users, who have verified their phonenumber usually get token rewards for their interactions on the site |
| `p2p_media_enabled` | bool | If webtorrent video is enabled, playback is usally slower and has less support for older browsers |
| `eth_wallet` | string | the attached Ethereum wallet of the user |
| `rating` | int | Output: 1 |
