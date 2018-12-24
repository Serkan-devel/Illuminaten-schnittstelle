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