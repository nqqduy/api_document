## # **Send SNS Kakao**

## **API Send SNS Kakao**

### **GET**

**Production**: [https://api.artnguide.co.kr/api/v1/auth/cb-kakao?code=&access_token=](https://api.artnguide.co.kr/api/v1/auth/cb-kakao?code=&access_token=

**Test**: [https://dev-api.artnguide.co.kr/api/v1/auth/cb-kakao?code=&access_token=](https://dev-api.artnguide.co.kr/api/v1/auth/cb-kakao?code=&access_token=)

## **REQUEST**

**Config header**:

none

**Data raw**

```json

```

### **Parameter**

|  Field   | Type   | Description     | required |
| :------: | ------ | --------------- | -------- |
|  email   | string | User's email    | yes      |
| userName | string | User's userName | yes      |

## **RESPONSE**

### **Moved Permanently 301**

redirect to: https://api.artnguide.co.kr/handleSNS-new?result=true&requiredVerify=true&resultCode=NEED_VERIFY&dataNice=kdjfgdfjkdjkfvgndjkfn123

### **ERROR 404 (Not Found)**

Temporarily not needed

```json
{}
```
