# API Documents

## Accounts

### Login

```
POST /api/users/login/
```

- Paremeters

| Parameter | Description | Notes                                                        |
| --------- | ----------- | ------------------------------------------------------------ |
| username  | Username    | max_length=20                                                |
| password  | Password    | Password should contain both numbers and English letters, with the length no less than 6 and no more than 20. |

- Return

Success example:

```json
{"id":1,"last_login":"2018-09-10T20:26:58.277522+08:00","username":"test","email":"test@test.com","avatar_url":"https://www.gravatar.com/avatar/b642b4217b34b1e8d3bd915fc65c4452?s=328&r=g&d=identicon","address":"","site_url":"","description":""}
```

Failed example:

```json
{"password":["This field is required."]}
```

```json
{"non_field_errors":["Username or password is incorrect."]}
```



### Register

```
POST /api/users/register/
```

- Paremeters

| Parameter | Description | Notes                                                        |
| --------- | ----------- | ------------------------------------------------------------ |
| username  | Username    | max_length=20                                                |
| email     | Email       |                                                              |
| password  | Password    | Password should contain both numbers and English letters, with the length no less than 6 and no more than 20. |

- Return

Success example:

```json
{
    "id": 1,
    "last_login": "2018-09-10T20:12:33.140150+08:00",
    "username": "test",
    "email": "test@test.com",
    "avatar_url": "https://www.gravatar.com/avatar/f2c97b1f2d2898cd2d6466ce95d4ba33?s=328&r=g&d=identicon",
    "address": "",
    "site_url": "",
    "description": ""
}
```

Failed example:

```json
{"username":["A user with that username already exists."],"email":["user with this email address already exists."]}
```

```json
{"username":["This field is required."],"email":["This field is required."],"password":["This field is required."]}
```

