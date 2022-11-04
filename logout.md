## # **Log Out**

## **Log Out**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/auth/logout](https://api.artnguide.co.kr/api/v1/auth/logout)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/auth/logout](https://dev-api.artnguide.co.kr/api/v1/auth/logout)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

Authorization: "bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"

**Data raw**

```json
{}
```

### **Parameter**

none

## **RESPONSE**

### **Success 200**

```json
{
  "result": true,
  "message": "Logout success",
  "data": null
}
```

### **ERROR 400**

```json
{
  "errorCode": true,
  "message": "VALIDATION ERROR Error: email is required!",
  "payload": [
    {
      "dataPath": "PCIVEN_1000&DEV_0001&SUBSYS_00000000&REV_02\1&08",
      "error": "email is required!"
    }
  ]
}
```

### **ERROR 403 (forbidden)**

```json
{}
```
