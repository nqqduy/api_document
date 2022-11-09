## # **Get Shipping Company By Id**

## **API Get Shipping Company By Id**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/shipping-company/get-by-id](https://api.artnguide.co.kr/api/v1/shipping-company/get-by-id)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/shipping-company/get-by-id](https://dev-api.artnguide.co.kr/api/v1/shipping-company/get-by-id)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

**Data raw**

```json
{
    "shippingCompanyId": 2
}
```

title

### **Parameter**

|       Field       | Type    | Description        | required |
| :---------------: | ------- | ------------------ | -------- |
| shippingCompanyId | integer | Shiping company id | yes      |

## **RESPONSE**

### **Success 200**

```json
{
    "result": true,
    "message": "Get shipping company by id successfully!",
    "data": {
        "id": 2,
        "trackingUrl": "https://www.tracking-url/2",
        "phone": "+840985489234",
        "displayOrder": 1,
        "createdBy": "2022-09-30T08:43:40.000Z",
        "updated_by": "2022-09-30T08:43:40.000Z",
        "isDeleted": false
    }
}
```

### **ERROR 400 (Bad Request)**

```json
{
    "errorCode": "Invalid_data",
    "message": "VALIDATION ERROR Error: Missing field \"shippingCompanyId\"!",
    "payload": [
        {
            "dataPath": "/faqId",
            "error": "Missing field \"shippingCompanyId\"!"
        }
    ]
}
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
