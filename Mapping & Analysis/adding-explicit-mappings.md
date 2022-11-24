# Adding explicit mapping

## Add field mappings for `reviews` index

```
PUT /reviews
{
   "mappings": {
      "properties": {
        "rating": { "type": "float" },
        "content": { "type": "text" },
        "product_id": { "type": "integer" },
        "author": {
          "properties": {
            "first_name": { "type": "text" }
            "last_name": { "type": "text" }
            "email": { "type": "keyword" }
          }
        }
      }
   }
}
```

## Index a text document
```
PUT /reviews/_doc/1
{
  "rating": 5.0,
  "content": "Outstanding course! Go really taught me a lot about Elasticsearch!",
  "author": {
    "first_name": "John",
    "last_name": "Doe",
    "email": "johndoe123@example.com"
  }
}
```