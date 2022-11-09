## # **Delete All Top Artist**

## **API Delete All Top Artist**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/top-artist/delete](https://api.artnguide.co.kr/api/v1/top-artist/delete)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/top-artist/delete](https://dev-api.artnguide.co.kr/api/v1/top-artist/delete)

## **REQUEST**

**Config header**:
Content-Type: "application/json"

Authorization: "bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"
**Data raw**

```json
{
    "id": 1
}
```

### **Parameter**

|     Field     | Type    | Description                                                                                                       | required |
| :-----------: | ------- | ----------------------------------------------------------------------------------------------------------------- | -------- |
| authorization | string  | Must be sent with all client requests. This Token helps server to validate request source. Provided by ARTNGUIDE. | yes      |
|      id       | integer | Top artist id                                                                                                     | yes      |

## **RESPONSE**

### **Success 200**

```json
{
    "result": true,
    "message": "Delete successfully!",
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
            "error": "Missing field 'id'!"
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
