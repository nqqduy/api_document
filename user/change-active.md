## # **Change User Activation**

## **API Change User Activation**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/user/change-active](https://api.artnguide.co.kr/api/v1/user/change-active)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/user/change-active](https://dev-api.artnguide.co.kr/api/v1/user/change-active)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

Authorization: "bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"

**Data raw**

```json
{
    "userId": 1,
    "active": true,
    "displayName":
}
```

### **Parameter**

|     Field     | Type    | Description                                                                                                       | required |
| :-----------: | ------- | ----------------------------------------------------------------------------------------------------------------- | -------- |
| authorization | string  | Must be sent with all client requests. This Token helps server to validate request source. Provided by ARTNGUIDE. | yes      |
|    userId     | integer | User's id                                                                                                         | yes      |
|    active     | boolean | active account                                                                                                    | yes      |
|  displayName  | string  | User's display name                                                                                               | no       |

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

```json
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
        "message": "Result not found!",
        "data": null,
        "errorCode": "user_404"
    }
}
```

```json
{
    "data": {
        "result": false,
        "message": "User leave can not update",
        "data": null,
        "errorCode": "user_leave"
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
