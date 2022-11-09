## # **Get All FAQ Category**

## **API Get All FAQ Category**

### **GET**

**Production**: [https://api.artnguide.co.kr/api/v1/faq/get-all-category?size=&page=&query=](https://api.artnguide.co.kr/api/v1/faq/get-all-category?size=&page=&query=)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/faq/get-all-category?size=&page=&query=](https://dev-api.artnguide.co.kr/api/v1/faq/get-all-category?size=&page=&query=)

## **REQUEST**

**Config header**:

Authorization: "bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"

**Data raw**

```
none

```

### **Parameter**

|     Field     | Type   | Description                                                                | required       |
| :-----------: | ------ | -------------------------------------------------------------------------- | -------------- |
| authorization | string | This Token helps server to validate request source. Provided by ARTNGUIDE. | no             |
|     page      | string | Page number to display                                                     | no default(1)  |
|     size      | string | Number of items displayed                                                  | no default(20) |
|     query     | string | Overall search like category code                                          | no             |

## **RESPONSE**

### **Success 200**

```json
{
{
    "result": true,
    "message": "ok",
    "data": {
        "datas": [
            {
                "id": 4,
                "categoryName": "공동구매",
                "categoryCode": "GP",
                "hierarchy": null,
                "createdBy": null,
                "isDeleted": false,
                "active": true,
                "displayOrder": 3,
                "createdAt": "2022-02-17T07:08:21.000Z",
                "updatedAt": "2022-02-17T07:08:21.000Z"
            },
            {
                "id": 5,
                "categoryName": "작품확인서",
                "categoryCode": "GP_SERIAL",
                "hierarchy": null,
                "createdBy": null,
                "isDeleted": false,
                "active": true,
                "displayOrder": 4,
                "createdAt": "2022-02-17T07:08:21.000Z",
                "updatedAt": "2022-02-17T07:08:21.000Z"
            },
            {
                "id": 6,
                "categoryName": "취화담",
                "categoryCode": "EXHIBITION",
                "hierarchy": null,
                "createdBy": null,
                "isDeleted": false,
                "active": true,
                "displayOrder": 5,
                "createdAt": "2022-02-17T07:08:21.000Z",
                "updatedAt": "2022-02-17T07:08:21.000Z"
            },
            {
                "id": 7,
                "categoryName": "회원관리",
                "categoryCode": "USER_MANAGE",
                "hierarchy": null,
                "createdBy": null,
                "isDeleted": false,
                "active": true,
                "displayOrder": 6,
                "createdAt": "2022-02-17T07:08:21.000Z",
                "updatedAt": "2022-02-17T07:08:21.000Z"
            },
            {
                "id": 8,
                "categoryName": "아트마켓",
                "categoryCode": "MARKET",
                "hierarchy": null,
                "createdBy": null,
                "isDeleted": false,
                "active": true,
                "displayOrder": 7,
                "createdAt": "2022-02-17T07:08:21.000Z",
                "updatedAt": "2022-02-17T07:08:21.000Z"
            }
        ],
        "pageable": {
            "totalElement": 5,
            "currentElement": 5,
            "totalPage": 1,
            "page": 1,
            "size": 100,
            "hasNext": false
        }
    }
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
    "result": false,
    "message": "404 not found!'",
    "data": null,
    "errorCode": "faq_category_404"
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
