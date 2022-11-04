## # **Sign In Sns**

## **API Sign In Sns**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/sign-in-sns](https://api.artnguide.co.kr/api/v1/auth/sign-in-sns)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/sign-in-sns](https://dev-api.artnguide.co.kr/api/v1/auth/sign-in-sns)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

**Data raw**

```json
{
  "snsAccessTokenOrCode": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c",
  "snsType": "NORMAL"
}
```

### **Parameter**

|        Field         | Type   | Description                     | required |
| :------------------: | ------ | ------------------------------- | -------- |
| snsAccessTokenOrCode | string | Token Or Code to accsess system | yes      |
|       snsType        | string | Type of sns                     | yes      |

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
      "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c",
      "requiredRegister": " "
    }
  }
}
```

### **ERROR 400**

```json
{
  "errorCode": true,
  "message": "VALIDATION ERROR Error: snsAccessTokenOrCode is required!",
  "payload": [
    {
      "dataPath": "PCIVEN_1000&DEV_0001&SUBSYS_00000000&REV_02\1&08",
      "error": "snsAccessTokenOrCode is required!"
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
