# Geeklog E-R diagram 

## Entity

- user
  - user_id: int
  - username: varchar
  - password: varchar
  - nickname: varchar
  - avatar(头像): varchar
  - bio(简介): varchar　
  - is_admin: bool
- star
  - star_id
  - user_id
  - article_id
- collect
  - collect_id
  - user_id
  - article_id
  - created_at: timestamp
- article
  - article_id
  - title
  - created_at: timestamp
  - modified_at: timestamp
  - user_id
  - content
  - category_id
  - tags
- comment
  - comment_id
  - user_id
  - content
  - parent_id
  - root_id
  - created_at: timestamp
- category
  - category_id
  - name
  - description
- authority
  - authority_id
  - name
- forbidden
  - forbidden_id
  - user_id
  - authority_id

```json
{
    "name": "1",
    "right": {
        "canComment": true,
        "canWrite": true
    }
}
```
