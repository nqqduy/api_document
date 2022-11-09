## # **Delete Partnership**

## **API Delete Partnership**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/partnership/del](https://api.artnguide.co.kr/api/v1/partnership/del)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/partnership/del](https://dev-api.artnguide.co.kr/api/v1/partnership/del)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

Authorization: "bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"

**Data raw**

```json
{
    "id": 1
}
```

### **Parameter**

|     Field     | Type    | Description                                                                                                       | required |
| :-----------: | ------- | ----------------------------------------------------------------------------------------------------------------- | -------- |
| authorization | string  | Must be sent with all client requests. This Token helps server to validate request source. Provided by ARTNGUIDE. | yes      |
|      id       | integer | Partnership's id.                                                                                                 | yes      |

## **RESPONSE**

### **Success 200**

```json
{
    "result": true,
    "message": "Del partnership success !",
    "data": null
}
```

### **ERROR 400 (Bad Request)**

```json
{
    "errorCode": "Invalid_data",
    "message": "VALIDATION ERROR Error: id is required!",
    "payload": [
        {
            "dataPath": "PCIVEN_1000&DEV_0001&SUBSYS_00000000&REV_021&08",
            "error": "id is required!"
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
    "message": "Partnership not found",
    "data": null,
    "errorCode": "partnership_404"
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
