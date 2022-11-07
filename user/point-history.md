## # **Get Point History**

## **API Get Point History**

### **GET**

**Production**: [https://api.artnguide.co.kr/api/v1/user/point-history?size=&page=&userId=](https://api.artnguide.co.kr/api/v1/user/point-history?size=&page=&userId=)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/user/point-history?size=&page=&userId=](https://dev-api.artnguide.co.kr/api/v1/user/point-history?size=&page=&userId=)

## **REQUEST**

**Config header**:

Authorization: "bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"

**Data raw**

```
none
```

### **Parameter**

|     Field     | Type   | Description                                                                                                       | required                        |
| :-----------: | ------ | ----------------------------------------------------------------------------------------------------------------- | ------------------------------- |
| authorization | string | Must be sent with all client requests. This Token helps server to validate request source. Provided by ARTNGUIDE. | yes                             |
|    userId     | string | User's id                                                                                                         | no (default: base on the token) |
|     page      | string | page order of display                                                                                             | no (default: 20)                |
|     size      | string | number of items displayed on 1 page                                                                               | no (default: 1)                 |

## **RESPONSE**

### **Success 200**

```json
{
    "data": {
        "result": true,
        "message": "ok!",
        "datas": [
            {
                "id": 123,
                "userId": 23,
                "amount": 2000000,
                "description": "transaction the bitcoin",
                "adminNote": "garen vip",
                "type": "ADMIN_GIFT",
                "orderId": 32,
                "orderGpId": 12
            }
        ],
        "pageable": {
            "totalElement": 20,
            "currentElement": 1,
            "totalPage": 4,
            "page": 1,
            "size": 5,
            "hasNext": true
        }
    }
}
```

### **ERROR 400 (Bad Request)**

```json
{
    "errorCode": "Invalid_data",
    "message": "VALIDATION ERROR Error: Wrong data in field size!",
    "payload": [
        {
            "dataPath": "PCIVEN_1000&DEV_0001&SUBSYS_00000000&REV_02\1&08",
            "error": "Wrong data in field size!"
        }
    ]
}
```

### **ERROR 401 (Unauthorized Error)**

```
Unauthorized
```

### **ERROR 404 (Not Found)**

```json
{
    "data": {
        "result": false,
        "message": "Result not found!",
        "data": null,
        "errorCode": "user_001"
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
