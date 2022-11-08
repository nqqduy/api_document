## # **Get All Article**

## **API Get All Article**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/article/get-all](https://api.artnguide.co.kr/api/v1/article/get-all)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/article/get-all](https://dev-api.artnguide.co.kr/api/v1/article/get-all)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

Authorization: "bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"

**Data raw**

```json
{
    "categoryCode": "TEMP",
    "endTime": "",
    "hashtag": "",
    "page": "",
    "query": "",
    "size": "12",
    "startTime": ""
}
```

### **Parameter**

|     Field     | Type   | Description                                                                | required |
| :-----------: | ------ | -------------------------------------------------------------------------- | -------- |
| authorization | string | This Token helps server to validate request source. Provided by ARTNGUIDE. | no       |
|     page      | string | Page number to display                                                     | yes      |
|     size      | string | Number of items displayed                                                  | yes      |
|     query     | string | Overall search like title, contents and hashtags                           | yes      |
|   startTime   | string | Search the article after the date of creation                              | yes      |
|    endTime    | string | Search the article before the date of creation                             | yes      |
|  titleSearch  | string | Search by title                                                            | no       |
| contentSearch | string | Search by content                                                          | no       |
| authorSearch  | string | Search by author                                                           | no       |
|  categories   | string | Article category code                                                      | no       |

## **RESPONSE**

### **Success 200**

```json
{
    "datas": [
        {
            "id": 419,
            "title": "프리즈가 남긴 숙제",
            "thumbnail": "https://artnguide.s3.ap-northeast-2.amazonaws.com/article/artng_1665987482892_%EC%95%A0%EB%84%90%EB%A6%AC%EC%8A%A4%ED%8A%B8%20%EB%A6%AC%ED%8F%AC%ED%8A%B8.png",
            "content": null,
            "views": 91,
            "categoryId": 12,
            "displayOrder": 1,
            "publisher": 22326,
            "updatedBy": null,
            "isDeleted": false,
            "createdAt": "2022-10-17T06:18:03.000Z",
            "updatedAt": "2022-10-17T06:18:03.000Z",
            "authorName": "admin 90",
            "active": true,
            "hashtag": ["vol.158", "158", "프리즈서울", "키아프", "kiaf", "이우환", "야요이쿠사마", "박서보", "이배"],
            "newsletterVol": null,
            "newsletterTitle1": null,
            "newsletterSummary1": null,
            "newsletterTitle2": null,
            "newsletterSummary2": null,
            "categoryCode": "TEMP"
        }
    ],

    "pageable": {
        "totalElement": 30,
        "currentElement": 12,
        "totalPage": 3,
        "page": 1,
        "size": 12,
        "hasNext": true
    }
}
```

### **ERROR 400 (Bad Request)**

```json
{
    "errorCode": "Invalid_data",
    "message": "VALIDATION ERROR Error: Missing field: page!",
    "payload": [
        {
            "dataPath": "PCIVEN_1000&DEV_0001&SUBSYS_00000000&REV_021&08",
            "error": "Missing field: page!"
        }
    ]
}
```

### **ERROR 404 (Not Found)**

```json
{
    "code": 404,
    "data": {
        "result": false,
        "message": "404 not found!",
        "data": null,
        "errorCode": "article_404"
    }
}
```

```json
{
    "code": 404,
    "data": {
        "result": false,
        "message": "No article category found!",
        "data": null,
        "errorCode": "article_c_404"
    }
}
```

### **ERROR 500 (Internal Server Error)**

```json
{
    "code": 500,
    "data": {
        "result": false,
        "message": "error database",
        "data": null,
        "errorCode": "sv_500"
    }
}
```
