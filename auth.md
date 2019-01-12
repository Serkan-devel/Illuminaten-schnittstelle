# Authentication

Current authentication-method is only [HTTP Basic Authentication](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Authorization).

Minds staff still developing on OAuth-support to make this process more secure.

## Login to Minds.com with your username and password
### `/api/v1/authenticate`
* Method: `POST`
* Request:

|Parameters|Function|Example|
|---|:---:|---:|
|username|Your username|medworthy|
|password|Your password|***|

* Response:

|Parameters|Function|Example output|
|---|:---:|---:|
|`success`|displays status of success|"success"|
|`user`|gives output of user||

<<<<<<< HEAD
* Note: You need to pass xsrf-tokens and cookies on the http-header
=======

## Authenticate with messenger
### `https://www.minds.com/api/v2/messenger/keys/unlock`
* Method: `POST`
* Request params dict:
    * `password` - Add you password next to it
* JSON Response: 
    * `{"status":"success"}`
* Cookie Response: 
    * `messenger-secret`

>>>>>>> ef828f8... move messenger authentication to auth.me
