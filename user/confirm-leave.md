## # **Confirm Leave**

## **API Confirm Leave**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/user/confirm-leave](https://api.artnguide.co.kr/api/v1/user/confirm-leave)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/user/confirm-leave](https://dev-api.artnguide.co.kr/api/v1/user/confirm-leave)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

Authorization: "bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"

**Data raw**

```json
{
    "userId": 1,
    "confirmLeave": true
}
```

### **Parameter**

|     Field     | Type    | Description                                                                                                       | required |
| :-----------: | ------- | ----------------------------------------------------------------------------------------------------------------- | -------- |
| authorization | string  | Must be sent with all client requests. This Token helps server to validate request source. Provided by ARTNGUIDE. | yes      |
|    userId     | integer | User's id                                                                                                         | yes      |
| confirmLeave  | boolean | Confirm leave or not                                                                                              | yes      |

## **RESPONSE**

### **Success 200**

```json
{
    "data": {
        "result": true,
        "message": "Update information ok!",
        "datas": null
    }
}
```

### **ERROR 400 (Bad Request)**

```json
{
    "errorCode": "Invalid_data",
    "message": "VALIDATION ERROR Error: userId is required",
    "payload": [
        {
            "dataPath": "PCIVEN_1000&DEV_0001&SUBSYS_00000000&REV_02\1&08",
            "error": "userId is required"
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
    "data": {
        "result": false,
        "message": "User not found!",
        "data": null,
        "errorCode": "user_404"
    }
}
```

```json
{
    "data": {
        "result": false,
        "message": "User not request leave",
        "data": null,
        "errorCode": "user_002"
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
