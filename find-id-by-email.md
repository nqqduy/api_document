## # **Find The User ID Sent By Email**

## **Find The User ID Sent By Email**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/auth/find-id](https://api.artnguide.co.kr/api/v1/auth/find-id)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/auth/find-id](https://dev-api.artnguide.co.kr/api/v1/auth/find-id)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

**Data raw**

```json
{
  "email": "duynguyen123@gmail.com"
}
```

### **Parameter**

| Field | Type   | Description  | required |
| :---: | ------ | ------------ | -------- |
| email | string | User's email | yes      |

## **RESPONSE**

### **Success 200**

```json
{
  "data": {
    "result": true,
    "message": "Id will send to your email!",
    "data": null
  }
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

### **ERROR 404**

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
