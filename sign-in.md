## # **Sign In**

## **API Sign In**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/auth/sign-in](https://api.artnguide.co.kr/api/v1/auth/sign-in)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/auth/sign-in](https://dev-api.artnguide.co.kr/api/v1/auth/sign-in)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

**Data raw**

```json
{
  "username": "antnguide",
  "password": "antnguide"
}
```

### **Parameter**

|  Field   | Type   | Description     | required |
| :------: | ------ | --------------- | -------- |
| userName | string | User's username | yes      |
| password | string | User's password | yes      |

## **RESPONSE**

### **Success 200**

```json
{
  "data": {
    "result": true,
    "message": "Sign in successfully!",
    "data": {
      "id": 1,
      "userName": "antnguide",
      "avatar": "duynguyen",
      "accountType": "NORMAL",
      "userRole": "ADMIN",
      "displayName": "duy nguyen",
      "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"
    }
  }
}
```

### **ERROR 400**

```json
{
  "errorCode": true,
  "message": "VALIDATION ERROR Error: userName is required!",
  "payload": [
    {
      "dataPath": "PCIVEN_1000&DEV_0001&SUBSYS_00000000&REV_02\1&08",
      "error": "userName is required!"
    }
  ]
}
```

### **ERROR 500**

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
