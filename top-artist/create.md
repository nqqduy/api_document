## # **Get All Top Artist**

## **API Get All Top Artist**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/top-artist/create](https://api.artnguide.co.kr/api/v1/top-artist/create)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/top-artist/create](https://dev-api.artnguide.co.kr/api/v1/top-artist/create)

## **REQUEST**

**Config header**:

**Data raw**

```json
{
    "authorName": "faker",
    "productName": "draw product",
    "price": 5000000,
    "tradeDay": "2022-08-30T08:45:52.000Z",
    "exhibitionDestination": "seoul, korea"
}
```

### **Parameter**

|         Field         | Type    | Description         | required |
| :-------------------: | ------- | ------------------- | -------- |
|      authorName       | string  | Author name         | yes      |
|      productName      | string  | Product name        | yes      |
|         price         | integer | Final selling price | yes      |
|       tradeDay        | string  | Sale date           | yes      |
| exhibitionDestination | string  | Selling place       | yes      |

## **RESPONSE**

### **Success 200**

```json
{
    "result": true,
    "message": "'Create successfully!",
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
