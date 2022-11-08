## # **Edit Article**

## **API Edit Article**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/article/edit](https://api.artnguide.co.kr/api/v1/article/edit)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/article/edit](https://dev-api.artnguide.co.kr/api/v1/article/edit)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

Authorization: "bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"

**Data raw**

```json
{
    "articleId": 12,
    "categoryId": 1,
    "title": "blockchain today",
    "content": "article content",
    "thumbnail": "https://www.aws.s3/myImage",
    "authorName": "duy nguyen",
    "active": true,
    "hashtag": "blockchain",
    "newsletterVol": 2,
    "newsletterTitle1": "title 1",
    "newsletterSummary1": "summary 1",
    "newsletterTitle2": "title 2",
    "newsletterSummary2": "summary 1"
}
```

### **Parameter**

|       Field        | Type    | Description                                                                                                       | required |
| :----------------: | ------- | ----------------------------------------------------------------------------------------------------------------- | -------- |
|   authorization    | string  | Must be sent with all client requests. This Token helps server to validate request source. Provided by ARTNGUIDE. | yes      |
|     articleId      | integer | Article article id                                                                                                | yes      |
|     categoryId     | integer | Article category id                                                                                               | yes      |
|       title        | string  | Article title                                                                                                     | yes      |
|      content       | string  | Article content                                                                                                   | yes      |
|       active       | string  | The status of the article is active or not                                                                        | yes      |
|     thumbnail      | string  | The url of image first appear in content                                                                          | no       |
|     authorName     | string  | Author name of article, maybe different publisher                                                                 | no       |
|      hashtag       | string  | Article hashtag                                                                                                   | no       |
|   newsletterVol    | string  | if the article is newsletter, need a newsletter Volumne                                                           | no       |
|  newsletterTitle1  | string  | newsletter Title 1                                                                                                | no       |
|  newsletterTitle1  | string  | newsletter Title 1                                                                                                | no       |
| newsletterSummary1 | string  | newsletter Summary 1                                                                                              | no       |
|  newsletterTitle2  | string  | newsletter Title 2                                                                                                | no       |
| newsletterSummary2 | string  | newsletter Summary 2                                                                                              | no       |

## **RESPONSE**

### **Success 200**

```json
{
    "data": {
        "result": true,
        "message": "Create successfully!",
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

```json
{
    "data": {
        "result": false,
        "message": "Field 'vol' is required",
        "data": null,
        "errorCode": "article_400"
    }
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
        "message": "Category not found!",
        "data": null,
        "errorCode": "article_404"
    }
}
```

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

### **ERROR 406 (Not Acceptable)**

```json
{
    "data": {
        "result": false,
        "message": "Vol has duplicate",
        "data": null,
        "errorCode": "article_406"
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
