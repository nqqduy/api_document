## # **Get Top Artist By Id**

## **API Get Top Artist By Id**

### **GET**

**Production**: [https://api.artnguide.co.kr/api/v1/top-artist/get-by-id?id=](https://api.artnguide.co.kr/api/v1/top-artist/get-by-id?id=)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/top-artist/get-all?page=&size=&query=&startTime=&endTime=](https://dev-api.artnguide.co.kr/api/v1/top-artist/get-by-id?id=)

## **REQUEST**

**Config header**:

**Data raw**

```
none
```

### **Parameter**

| Field | Type   | Description   | required |
| :---: | ------ | ------------- | -------- |
|  id   | string | Top artist id | yes      |

## **RESPONSE**

### **Success 200**

```json
{
    "result": true,
    "message": "Get detail successfully!",
    "data": {
        "id": 1,
        "rank": 1,
        "authorName": "야요이 쿠사마",
        "productName": " Pumpkin (2004)",
        "price": 1950000000,
        "tradeDay": "2022-09-27T07:00:00.000Z",
        "exhibitionDestination": "서울옥션",
        "createdAt": "2022-05-12T02:29:41.000Z",
        "updatedAt": "2022-05-12T02:29:41.000Z"
    }
}
```

### **ERROR 400 (Bad Request)**

```json
{
    "errorCode": "invalid_data",
    "message": "VALIDATION ERROR Error: Missing field 'id'!",
    "payload": [
        {
            "dataPath": "./id",
            "error": "Missing field 'id'!"
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
    "result": false,
    "message": "No data found!",
    "data": null,
    "errorCode": null
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
