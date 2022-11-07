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

|     Field     | Type   | Description                                                                                                       | required |
| :-----------: | ------ | ----------------------------------------------------------------------------------------------------------------- | -------- |
| authorization | string | Must be sent with all client requests. This Token helps server to validate request source. Provided by ARTNGUIDE. | yes      |

## **RESPONSE**

### **Success 200**

```json
{
  "result": true,
  "message": "Logout success",
  "data": null
}
```

### **ERROR 401 (Unauthorized Error)**

```json
{}
```

### **ERROR 403 (forbidden)**

```json
{}
```
