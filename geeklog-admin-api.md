# Geeklog Api

## 管理后台Api(/admin/*)

### User

GET /admin/users?page=1&size=20 (不返回admin))

res:

```json
{
    "code": 700,
    "message": "Success or failure",
    "data": {
        "total": 342,
        "users": [
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
            }
        ]
    }
}
```

### Forbidden

POST /admin/forbiddens

req:

```json
{
    "user_id": 1,
    "authority_id": 1
}
```

res:

```json
{
    "code": 200,
    "message": "Success or failure..",
    "data": {
        "forbidden_id": 1,
        "user_id": 1,
        "authority_id": 1
    }
}
```

DELETE /admin/forbiddens/:user_id/:authority_id

res:

```json
{
    "code": 200,
    "message": "Successfully deleted",
    "data": {
        "forbidden_id": 1,
        "user_id": 1,
        "authority_id": 1
    }
}
```

### Admin Login

POST /admin/login

req:

```json
{
    "username": "admin",
    "password": "123456"
}
```

res:

```json
{
    "code": 200,
    "message": "Success",
    "data": {
        "token": "12n3n12kkj21s"
    }
}
```

### Admin Article

GET /admin/articles?category_id=1&page=1&size=30

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

DELETE /admin/articles/:article_id

res:

```json
{
    "code": 200,
    "message": "Delete successfully",
    "data": {
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
}
```

PUT /admin/articles/:article_id

req:

```json
{
    "display": false
}
```

res:

```json
{
    "code": 200,
    "message": "success",
    "data": {
        "article_id": 2,
        "title": "a title",
        "created_at": 12211033,
        "modified_at": 16125652,
        "content": "some content",
        "user_id": 1,
        "category_id": 2,
        "tags": "java,python,sql",
        "display": false
    }
}
```

### Admin Comments

GET /admin/comments?article_id=2&root_id=1&page=1&size=30

res:

```json
{
    "code": 200,
    "message": "message",
    "data": {
        "total": 560,
        "comments": [
            {
                "comment_id": 1,
                "user_id": 1,
                "article_id": 2,
                "content": "some demo content",
                "parent_id": 2,
                "root_id": 1,
                "created_at": 1244213131
            },
            {
                "comment_id": 2,
                "user_id": 1,
                "article_id": 2,
                "content": "some demo content",
                "parent_id": 2,
                "root_id": 1,
                "created_at": 1244213131
            }
        ]
    }
}
```

DELETE /admin/comments/:comment_id

res:

```json
{
    "code": 200,
    "message": "success",
    "data": {
        "comment_id": 2,
        "user_id": 1,
        "article_id": 2,
        "content": "some demo content",
        "parent_id": 2,
        "root_id": 1,
        "created_at": 1244213131
    }
}
```

### Manage Category

GET /admin/categories

res:

```json
{
    "code": 200,
    "message": "fetch success",
    "data": [
        {
            "category_id": 1,
            "name": "frontend",
            "description": "some descr"
        },
        {
            "category_id": 2,
            "name": "frontend",
            "description": "some descr"
        }
    ]
}
```

POST /admin/categories

req:

```json
{
    "name": "a cate",
    "description": "describe it"
}
```

res:

```json
{
    "code": 200,
    "message": "success",
    "data": {
        "category_id": 2,
        "name": "back-end",
        "description": "other description"
    }
}
```

PUT /admin/categories/:category_id

req:

```json
{
    "name": "back-end",
    "description": "other description"
}
```

res:

```json
{
    "code": 200,
    "message": "success",
    "data": {
        "name": "back-end",
        "description": "other description"
    }
}
```

DELETE /admin/categories/:category_id

res:

```json
{
    "code": 200,
    "message": "success",
    "data": {
        "name": "back-end",
        "description": "other description"
    }
```

### Admin Authorities

GET /admin/authorities

res:

```json
{
    "code": 200,
    "message": "success",
    "data": [
        {
            "authority_id": 1,
            "name": "can_comment"
        },
        {
            "authority_id": 2,
            "name": "can_write_article"
        }
    ]
}
```
