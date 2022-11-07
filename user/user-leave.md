## # **User Leave**

## **API User Leave**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/user/leave](https://api.artnguide.co.kr/api/v1/user/leave)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/user/leave](https://dev-api.artnguide.co.kr/api/v1/user/leave)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

Authorization: "bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"

**Data raw**

```
none
```

### **Parameter**

|     Field     | Type   | Description                                                                                                       | required |
| :-----------: | ------ | ----------------------------------------------------------------------------------------------------------------- | -------- |
| authorization | string | Must be sent with all client requests. This Token helps server to validate request source. Provided by ARTNGUIDE. | yes      |

## **RESPONSE**

### **Success 200**

```json
{
    "data": {
        "result": true,
        "message": "ok!",
        "datas": null
    }
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
        "message": "error database",
        "data": null,
        "errorCode": "sv_500"
    }
}
```
