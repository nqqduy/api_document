## # **Update Shipping company**

## **API Update Shipping company**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/shipping-company/update](https://api.artnguide.co.kr/api/v1/shipping-company/update)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/shipping-company/update](https://dev-api.artnguide.co.kr/api/v1/shipping-company/update)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

Authorization: "bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"

**Data raw**

```json
{
    "shippingCompanyId": 1,
    "name": "기존 안드로이드 앱은 사용할 수 없나요?",
    "trackingUrl": "https://www.tracking-url.com/myTracking",
    "phone": "+84987456123",
    "displayOrder": 1
}
```

### **Parameter**

|       Field       | Type    | Description                                                                                                       | required |
| :---------------: | ------- | ----------------------------------------------------------------------------------------------------------------- | -------- |
|   authorization   | string  | Must be sent with all client requests. This Token helps server to validate request source. Provided by ARTNGUIDE. | yes      |
|       name        | string  | Shipping company name                                                                                             | yes      |
| shippingCompanyId | integer | Shipping company id                                                                                               | yes      |
|    trackingUrl    | string  | Tracking url                                                                                                      | yes      |
|       phone       | string  | Shipping company phone                                                                                            | yes      |
|   displayOrder    | integer | Display order                                                                                                     | yes      |

## **RESPONSE**

### **Success 200**

```json
{
    "result": true,
    "message": "Update shipping company successfully!",
    "data": null
}
```

### **ERROR 400 (Bad Request)**

```json
{
    "errorCode": "Invalid_data",
    "message": "VALIDATION ERROR Error: Missing field 'shippingCompanyId'!",
    "payload": [
        {
            "dataPath": "PCIVEN_1000&DEV_0001&SUBSYS_00000000&REV_021&08",
            "error": "Missing field 'shippingCompanyId'!"
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
    "message": "No not found!",
    "data": null,
    "errorCode": "ship_404"
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
