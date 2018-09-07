# Geeklog Api

## 管理后台Api(/admin/*)

### User

GET /admin/users?page=1&size=20 (不返回admin))

res:

```json
{
    "code": 700,
    "message": "Success or failure",
    "data": [
        {
            "user_id": 1,
            "username": "loginname",
            "nickname": "a-nick-name",
            "avatar": "http://....",
            "is_admin": false,
            "can_comment": true,
            "can_write": true
        },
        {
            "user_id": 2,
            "username": "loginname",
            "nickname": "a-nick-name",
            "avatar": "http://....",
            "is_admin": false,
            "can_comment": true,
            "can_write_article": true
        },
    ]
}
```

### Forbidden

POST /admin/forbiddens

req:

```json
{
    "user_id": "uid",
    "authority_name": "can_comment"
}
```

res:

```json
{
    "code": 200,
    "message": "Success or failure..",
    "data": {
        "user_id": "uid",
        "authority_name": "can_comment"
    }
}
```
