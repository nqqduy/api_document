## # **Update All Top Artist**

## **API Update All Top Artist**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/top-artist/update](https://api.artnguide.co.kr/api/v1/top-artist/update)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/top-artist/update](https://dev-api.artnguide.co.kr/api/v1/top-artist/update)

## **REQUEST**

**Config header**:
Content-Type: "application/json"

Authorization: "bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"
**Data raw**

```json
{
    "id": 1,
    "authorName": "faker",
    "productName": "draw product",
    "price": 5000000,
    "tradeDay": "2022-08-30T08:45:52.000Z",
    "exhibitionDestination": "seoul, korea"
}
```

### **Parameter**

|         Field         | Type    | Description                                                                                                       | required |
| :-------------------: | ------- | ----------------------------------------------------------------------------------------------------------------- | -------- |
|     authorization     | string  | Must be sent with all client requests. This Token helps server to validate request source. Provided by ARTNGUIDE. | yes      |
|          id           | integer | Top artist id                                                                                                     | yes      |
|      authorName       | string  | Author name                                                                                                       | yes      |
|      productName      | string  | Product name                                                                                                      | yes      |
|         price         | integer | Final selling price                                                                                               | yes      |
|       tradeDay        | string  | Sale date                                                                                                         | yes      |
| exhibitionDestination | string  | Selling place                                                                                                     | yes      |

## **RESPONSE**

### **Success 200**

```json
{
    "result": true,
    "message": "Update successfully!",
    "data": null
}
```

### **ERROR 400 (Bad Request)**

```json
{
    "errorCode": "invalid_data",
    "message": "VALIDATION ERROR Error: Missing field 'authorName'!",
    "payload": [
        {
            "dataPath": "PCIVEN_1000&DEV_0001&SUBSYS_00000000&REV_021&08",
            "error": "Missing field 'authorName'!"
        }
    ]
}
```

### **ERROR 404 (Not Found)**

```json
{
    "result": false,
    "message": "No data found!",
    "data": null,
    "errorCode": "ta_404"
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
