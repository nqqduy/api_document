## # **Change Password**

## **API Change Password**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/auth/change-password](https://api.artnguide.co.kr/api/v1/auth/change-password)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/auth/change-password](https://dev-api.artnguide.co.kr/api/v1/auth/change-password)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

Authorization: "bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"

**Data raw**

```json
{
  "newPassword": "antnguide",
  "oldPassword": "antnguide"
}
```

### **Parameter**

|     Field     | Type   | Description                                                                                                       | required |
| :-----------: | ------ | ----------------------------------------------------------------------------------------------------------------- | -------- |
|  newPassword  | string | User's new password                                                                                               | yes      |
|  oldPassword  | string | User's old password                                                                                               | yes      |
| authorization | string | Must be sent with all client requests. This Token helps server to validate request source. Provided by ARTNGUIDE. | yes      |

## **RESPONSE**

### **Success 200**

```json
{
  "data": {
    "result": true,
    "message": "Change password successfully!",
    "data": null
  }
}
```

### **ERROR 403 (forbidden)**

```json
{}
```

### **ERROR 400 (Bad Request)**

```json
{
  "errorCode": "invalid_data",
  "message": "VALIDATION ERROR Error: oldPassword is required!",
  "payload": [
    {
      "dataPath": "PCIVEN_1000&DEV_0001&SUBSYS_00000000&REV_02\1&08",
      "error": "oldPassword is required!"
    }
  ]
}
```

### **ERROR 404 (Not Found)**

```json
{
  "data": {
    "result": false,
    "message": "User not found!",
    "data": null,
    "errorCode": "auh_404"
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
