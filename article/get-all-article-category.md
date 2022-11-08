## # **Get All Article Category**

## **API Get All Article Category**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/article/get-all-category](https://api.artnguide.co.kr/api/v1/article/get-all-category)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/article/get-all-category](https://dev-api.artnguide.co.kr/api/v1/article/get-all-category)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

**Data raw**
https://www.google.com:3000/

```json
{
    "page": "1",
    "size": "100",
    "categoryCode": "TEMP"
}
```

### **Parameter**

|    Field     | Type   | Description               | required         |
| :----------: | ------ | ------------------------- | ---------------- |
|     page     | string | Page number to display    | no (default: 1)  |
|     size     | string | Number of items displayed | no (default: 20) |
| categoryCode | string | Article category code     | no               |

## **RESPONSE**

### **Success 200**

```json
{
    "datas": [
        {
            "id": 4,
            "categoryName": "notice",
            "categoryCode": "NOTICE",
            "hierarchy": null,
            "hierarchyCode": null,
            "createdBy": null,
            "isDeleted": false,
            "createdAt": "2022-07-20T09:18:06.000Z",
            "updatedAt": "2022-07-20T09:18:06.000Z",
            "subCategories": [
                {
                    "id": 7,
                    "category_name": "공지 - thông báo",
                    "category_code": "NOTICE_ANNOUCEMENT",
                    "hierarchy": 4,
                    "hierarchy_code": "NOTICE",
                    "created_by": null,
                    "is_deleted": false,
                    "created_at": "2022-07-20T09:18:07.000Z",
                    "updated_at": "2022-07-20T09:18:07.000Z"
                },
                {
                    "id": 8,
                    "category_name": "매각 - bán/sang nhượng",
                    "category_code": "NOTICE_GPSALES",
                    "hierarchy": 4,
                    "hierarchy_code": "NOTICE",
                    "created_by": null,
                    "is_deleted": false,
                    "created_at": "2022-07-20T09:18:07.000Z",
                    "updated_at": "2022-07-20T09:18:07.000Z"
                }
            ]
        },
        {
            "id": 5,
            "categoryName": "NEWS",
            "categoryCode": "NEWS",
            "hierarchy": null,
            "hierarchyCode": null,
            "createdBy": null,
            "isDeleted": false,
            "createdAt": "2022-07-20T09:18:06.000Z",
            "updatedAt": "2022-07-20T09:18:06.000Z",
            "subCategories": []
        }
    ],
    "pageable": {
        "totalElement": 7,
        "currentElement": 7,
        "totalPage": 1,
        "page": 1,
        "size": 100,
        "hasNext": false
    }
}
```

### **ERROR 404 (Not Found)**

```json
{
    "code": 400,
    "data": {
        "result": false,
        "message": "No article category found!",
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
