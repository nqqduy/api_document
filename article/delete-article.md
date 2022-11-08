## # **Delete Article**

## **API Delete Article**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/article/delete](https://api.artnguide.co.kr/api/v1/article/delete)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/article/delete](https://dev-api.artnguide.co.kr/api/v1/article/delete)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

Authorization: "bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"

**Data raw**

```json
{
    "articleId": 12
}
```

### **Parameter**

|     Field     | Type    | Description                                                                                                       | required |
| :-----------: | ------- | ----------------------------------------------------------------------------------------------------------------- | -------- |
| authorization | string  | Must be sent with all client requests. This Token helps server to validate request source. Provided by ARTNGUIDE. | yes      |
|   articleId   | integer | Article article id                                                                                                | yes      |

## **RESPONSE**

### **Success 200**

```json
{
    "data": {
        "result": true,
        "message": "Delete successfully!",
        "datas": null
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

### **ERROR 401 (Unauthorized Error)**

```
Unauthorized

```

### **ERROR 403 (forbidden)**

```text
Only for admin
```

### **ERROR 404 (Not Found)**

```json
{
    "data": {
        "result": false,
        "message": "Article not found!",
        "data": null,
        "errorCode": "article_404"
    }
}
```

### **ERROR 500 (Internal Server Error)**

```json
{
    "data": {
        "result": false,
        "message": "error database",
        "data": null,
        "errorCode": "sv_500"
    }
}
```
