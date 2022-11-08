## # **Get New And Old Of Article**

## **Get New And Old Of Article**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/article/next-prev](https://api.artnguide.co.kr/api/v1/article/next-prev)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/article/next-prev](https://dev-api.artnguide.co.kr/api/v1/article/next-prev)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

**Data raw**

```json
{
    "articleId": 12
}
```

### **Parameter**

|   Field   | Type    | Description        | required |
| :-------: | ------- | ------------------ | -------- |
| articleId | integer | Article article id | yes      |

## **RESPONSE**

### **Success 200**

```json
{
    "result": true,
    "message": "Find article page successfully!",
    "data": {
        "newestArticle": {
            "id": 1,
            "category_id": 2,
            "title": "blockchain",
            "thumbnail": "https://www.aws.s3/myThubnail"
        },
        "oldestArticle": {
            "id": 100,
            "category_id": 2,
            "title": "blockchain100",
            "thumbnail": "https://www.aws.s3/myThubnail100"
        }
    }
}
```

### **ERROR 400 (Bad Request)**

```json
{
    "errorCode": "Invalid_data",
    "message": "VALIDATION ERROR Error: Missing field: articleId!",
    "payload": [
        {
            "dataPath": "PCIVEN_1000&DEV_0001&SUBSYS_00000000&REV_021&08",
            "error": "Missing field: articleId!"
        }
    ]
}
```

### **ERROR 404 (Not Found)**

```json
{
    "result": false,
    "message": "Article not found!",
    "data": null,
    "errorCode": "article_404"
}
```

### **ERROR 500 (Internal Server Error)**

```json
{
    "result": false,
    "message": "error database",
    "data": null,
    "errorCode": "sv_500"
}
```
