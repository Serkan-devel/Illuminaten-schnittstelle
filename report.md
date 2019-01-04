## Reporting

### `/api/v1/entities/report/{base64 of comment}`
#### Reporting a comment
* Method: `POST`
* Request json:

| Parameter | type | Description |
| --- |:---:| ---:|
| `subject` | int | The reason for the report. For Spam, it's an `8` |
| `note` | string | What the user enters when selecting "Another reason" |

* Response: `{"status":"success","done":true}`
