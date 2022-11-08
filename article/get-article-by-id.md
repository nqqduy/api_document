## # **Get Article By Id**

## **API Get Article By Id**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/article/get-by-id](https://api.artnguide.co.kr/api/v1/article/get-by-id)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/article/get-by-id](https://dev-api.artnguide.co.kr/api/v1/article/get-by-id)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

Authorization: "bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"

**Data raw**

```json
{
    "articleId": 1
}
```

### **Parameter**

|     Field     | Type    | Description                                                                | required |
| :-----------: | ------- | -------------------------------------------------------------------------- | -------- |
| authorization | string  | This Token helps server to validate request source. Provided by ARTNGUIDE. | no       |
|   articleId   | integer | Article id                                                                 | yes      |

## **RESPONSE**

### **Success 200**

```json
{
    "result": true,
    "message": "Get article by id successfully!",
    "data": {
        "id": 10,
        "title": "title 1-10",
        "thumbnail": null,
        "content": "https://www.youtube.com/embed/1bBFYIB4pLI",
        "views": 1,
        "categoryId": 3,
        "displayOrder": 1,
        "publisher": 1,
        "updatedBy": null,
        "isDeleted": false,
        "createdAt": "2022-02-16T08:33:43.000Z",
        "updatedAt": "2022-02-16T08:33:43.000Z",
        "authorName": "Admin 1",
        "active": true,
        "hashtag": null,
        "newsletterVol": null,
        "newsletterTitle1": null,
        "newsletterSummary1": null,
        "newsletterTitle2": null,
        "newsletterSummary2": null
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
