## # **Up Down FAQ**

## **API Up Down FAQ**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/faq/up-down-faq](https://api.artnguide.co.kr/api/v1/faq/up-down-faq)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/faq/up-down-faq](https://dev-api.artnguide.co.kr/api/v1/faq/up-down-faq)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

Authorization: "bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"

**Data raw**

```json
{
    "id": 97,
    "upDownMethod": "DOWN"
}
```

### **Parameter**

|     Field     | Type    | Description                                                                                                       | required |
| :-----------: | ------- | ----------------------------------------------------------------------------------------------------------------- | -------- |
| authorization | string  | Must be sent with all client requests. This Token helps server to validate request source. Provided by ARTNGUIDE. | yes      |
|     faqId     | integer | FAQ's id                                                                                                          | yes      |
| upDownMethod  | string  | up or down to find                                                                                                | yes      |

## **RESPONSE**

### **Success 200**

```json
{
    "result": true,
    "message": "No need up!",
    "data": null
}
```

```json
{
    "result": true,
    "message": "No need down!",
    "data": null
}
```

```json
{
    "result": true,
    "message": "Update successfully!",
    "data": null
}
```

### **ERROR 400 (Bad Request)**

```json
{
    "errorCode": "Invalid_data",
    "message": "VALIDATION ERROR Error: Missing field 'id'!",
    "payload": [
        {
            "dataPath": "PCIVEN_1000&DEV_0001&SUBSYS_00000000&REV_021&08",
            "error": "Missing field 'id'!"
        }
    ]
}
```

### **ERROR 401 (Unauthorized Error)**

```
Unauthorized

```

### **ERROR 403 (forbidden)**

```text
Only for admin
```

### **ERROR 404 (Not Found)**

```json
{
    "result": false,
    "message": "Faq not found!",
    "data": null,
    "errorCode": "faq_404"
}
```

### **ERROR 500 (Internal Server Error)**

```json
{
    "result": false,
    "message": "error database",
    "data": null,
    "errorCode": "sv_500"
}
```
