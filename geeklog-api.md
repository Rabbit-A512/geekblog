# Core Api of Geeklog

## User

### User Login

POST /login

req:

```json
{
    "username": "syf",
    "password": "123456"
}
```

res:

```json
{
    "code": 200,
    "message": "Success",
    "data": {
        "token": "1j312lnn21312"
    }
}
```

GET /users/:user_id

res:

```json
{
    "code": 200,
    "message": "Success",
    "data": {
        "user_id": 1,
        "username": "loginname",
        "nickname": "a-nick-name",
        "bio": "some info about me",
        "avatar": "http://....",
        "is_admin": false,
        "can_comment": true,
        "can_write_article": true
    }
}
```

POST /users (注册)

req:

```json
{
    "username": "syf",
    "password": "123456",
    "nickname": "rabbit-a512",
    "bio": "some info about me"
}
```

res:

```json
{
    "code": 200,
    "message": "success",
    "data": {
        "username": "loginname",
        "nickname": "a-nick-name",
        "avatar": "指向默认图片的路径",
        "bio": "some info about me",
        "is_admin": false,
        "can_comment": true,
        "can_write_article": true
    }
}
```

PUT /users/:user_id (头像路径单独维护)

req:

```json
{
    "nickname": "another",
    "password": "234567",
    "bio": "another bio"
}
```

DELETE (暂定不做)

## Article

GET /articles?page=1&size=30

res:

```json
{
    "code": 200,
    "message": "success",
    "data": {
        "total": 234,
        "articles": [
            {
                "article_id": 1,
                "title": "a title",
                "created_at": 12211033,
                "modified_at": 16125652,
                "content": "some content",
                "user_id": 1,
                "category_id": 2,
                "tags": "java,python,sql",
                "display": true
            },
            {
                "article_id": 2,
                "title": "a title",
                "created_at": 12211033,
                "modified_at": 16125652,
                "content": "some content",
                "user_id": 1,
                "category_id": 2,
                "tags": "java,python,sql",
                "display": true
            }
        ]
    }
}
```

POST /articles

req:

```json
{
    "title": "a title",
    "content": "more content",
    "user_id": 2,
    "category_id": 2,
    "tags": "vue,typescript,webpack"
}
```

res:

```json
{
    "code": 200,
    "message": "success",
    "data": {
        "article_id": 1,
        "title": "a title",
        "created_at": 12211033,
        "modified_at": 16125652,
        "content": "some content",
        "user_id": 1,
        "category_id": 2,
        "tags": "java,python,sql",
        "display": true
    }
}
```

PUT /articles/:article_id

req:

```json
{
    "title": "a title",
    "content": "more content",
    "category_id": 2,
    "tags": "vue,typescript,webpack"
}
```

res:

```json
{
    "code": 200,
    "message": "success",
    "data": {
        "article_id": 1,
        "title": "a title",
        "created_at": 12211033,
        "modified_at": 16125652,
        "content": "some content",
        "user_id": 1,
        "category_id": 2,
        "tags": "java,python,sql",
        "display": true
    }
}
```

DELETE /articles/:article_id

res:

```json
{
    "code": 200,
    "message": "success",
    "data": {
        "article_id": 1,
        "title": "a title",
        "created_at": 12211033,
        "modified_at": 16125652,
        "content": "some content",
        "user_id": 1,
        "category_id": 2,
        "tags": "java,python,sql",
        "display": true
    }
}
```

## Comment
