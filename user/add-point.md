## # **Add Point For User**

## **API Add Point For User**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/user/add-point](https://api.artnguide.co.kr/api/v1/user/admin-update-user-info)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/user/add-point](https://dev-api.artnguide.co.kr/api/v1/user/add-point)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

Authorization: "bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"

**Data raw**

```json
{
    "userId": 1,
    "amount": 2000000,
    "note": "nothing",
    "adminNote": "nothing"
}
```

### **Parameter**

|     Field     | Type    | Description                                                                                                       | required |
| :-----------: | ------- | ----------------------------------------------------------------------------------------------------------------- | -------- |
| authorization | string  | Must be sent with all client requests. This Token helps server to validate request source. Provided by ARTNGUIDE. | yes      |
|    userId     | integer | User's id                                                                                                         | yes      |
|    amount     | integer | amount will be add                                                                                                | yes      |
|   adminNote   | string  | Note of admin                                                                                                     | no       |
|     note      | string  | note name                                                                                                         | no       |

## **RESPONSE**

### **Success 200**

```json
{
    "data": {
        "result": true,
        "message": "Add 2000000 point success",
        "datas": null
    }
}
```

### **ERROR 400 (Bad Request)**

```json
{
    "errorCode": "Invalid_data",
    "message": "VALIDATION ERROR Error: wrong data in field userId",
    "payload": [
        {
            "dataPath": "PCIVEN_1000&DEV_0001&SUBSYS_00000000&REV_02\1&08",
            "error": "wrong data in field userId"
        }
    ]
}
```

### **ERROR 401 (Unauthorized Error)**

```
Unauthorized

```

### **ERROR 403 (Forbidden Error)**

```
Forbidden
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
        "message": "User not found!",
        "data": null,
        "errorCode": "user_404"
    }
}
```

### **ERROR 500 (Internal Server Error)**

```json
{
    "data": {
        "result": false,
        "message": "Amount must be not equals 0",
        "data": null,
        "errorCode": "common_invalid_input"
    }
}
```

```json
{
    "data": {
        "result": false,
        "message": "Not enough point to withdraw",
        "data": null,
        "errorCode": "common_invalid_input"
    }
}
```

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
