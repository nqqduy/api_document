## # **Recovery User Password**

## **Recovery User Password**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/auth/recovery-pw](https://api.artnguide.co.kr/api/v1/auth/recovery-pw)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/auth/recovery-pw](https://dev-api.artnguide.co.kr/api/v1/auth/recovery-pw)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

**Data raw**

```json
{
  "email": "duynguyen123@gmail.com",
  "userName": "antnguide"
}
```

### **Parameter**

|  Field   | Type   | Description     | required |
| :------: | ------ | --------------- | -------- |
|  email   | string | User's email    | yes      |
| userName | string | User's userName | yes      |

## **RESPONSE**

### **Success 200**

```json
{
  "data": {
    "result": true,
    "message": "Going to verified",
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
