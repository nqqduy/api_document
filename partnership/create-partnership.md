## # **Create Partnership**

## **API Create Partnership**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/partnership/create](https://api.artnguide.co.kr/api/v1/partnership/create)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/partnership/create](https://dev-api.artnguide.co.kr/api/v1/partnership/create)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

**Data raw**

```json
{
    "title": "blockchain",
    "agreePolicy": true,
    "contactPerson": "Faker",
    "optionName": "SKT T1",
    "phoneNumber": "+84987456123",
    "email": "faker@gmail.com",
    "content": "content ....",
    "division": "OTHER"
}
```

### **Parameter**

|     Field     | Type    | Description                                                        | required |
| :-----------: | ------- | ------------------------------------------------------------------ | -------- |
|     title     | string  | Cooperation title                                                  | yes      |
|  agreePolicy  | boolean | Agree to the terms                                                 | yes      |
| contactPerson | string  | Contact person                                                     | yes      |
|  optionName   | string  | Company name or organization name                                  | yes      |
|     email     | string  | Contact email                                                      | yes      |
|    content    | string  | Content request cooperation                                        | yes      |
|   division    | string  | Classification: public organization, enterprise, individual, other | yes      |
|  phoneNumber  | string  | Contact phone number title!                                        | yes      |

## **RESPONSE**

### **Success 200**

```json
{
    "result": true,
    "message": "Request partnership success !",
    "data": {
        "id": 23
    }
}
```

### **ERROR 400 (Bad Request)**

```json
{
    "errorCode": "Invalid_data",
    "message": "VALIDATION ERROR Error: title is required!",
    "payload": [
        {
            "dataPath": "PCIVEN_1000&DEV_0001&SUBSYS_00000000&REV_021&08",
            "error": "title is required!"
        }
    ]
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
