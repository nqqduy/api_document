## # **Update Partnership**

## **API Update Partnership**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/partnership/update](https://api.artnguide.co.kr/api/v1/partnership/update)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/partnership/update](https://dev-api.artnguide.co.kr/api/v1/partnership/update)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

Authorization: "bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"

**Data raw**

```json
{
    "id": 23,
    "title": "blockchain",
    "agreePolicy": true,
    "contactPerson": "Faker",
    "optionName": "SKT T1",
    "phoneNumber": "+84987456123",
    "email": "faker@gmail.com",
    "content": "content ....",
    "division": "OTHER",
    "confirm": true
}
```

### **Parameter**

|     Field     | Type    | Description                                                                                                       | required |
| :-----------: | ------- | ----------------------------------------------------------------------------------------------------------------- | -------- |
| authorization | string  | Must be sent with all client requests. This Token helps server to validate request source. Provided by ARTNGUIDE. | yes      |
|      id       | integer | Partnership's id                                                                                                  | yes      |
|     title     | string  | Cooperation title                                                                                                 | yes      |
|  agreePolicy  | boolean | Agree to the terms                                                                                                | yes      |
| contactPerson | string  | Contact person                                                                                                    | yes      |
|  optionName   | string  | Company name or organization name                                                                                 | yes      |
|     email     | string  | Contact email                                                                                                     | yes      |
|    content    | string  | Content request cooperation                                                                                       | yes      |
|   division    | string  | Classification: public organization, enterprise, individual, other                                                | yes      |
|  phoneNumber  | string  | Contact phone number title!                                                                                       | yes      |
|    confirm    | boolean | Do you agree to cooperate? title!                                                                                 | no       |

## **RESPONSE**

### **Success 200**

```json
{
    "result": true,
    "message": "Update partnership success !",
    "data": {
        "id": 23,
        "title": "blockchain",
        "agree_policy": true,
        "contact_person": "Faker",
        "option_name": "SKT T1",
        "phone_number": "+84987456123",
        "email": "faker@gmail.com",
        "content": "content ....",
        "division": "OTHER",
        "confirm": true,
        "is_deleted": false
    }
}
```

### **ERROR 400 (Bad Request)**

```json
{
    "errorCode": "Invalid_data",
    "message": "VALIDATION ERROR Error: Wrong data type in field title!",
    "payload": [
        {
            "dataPath": "PCIVEN_1000&DEV_0001&SUBSYS_00000000&REV_021&08",
            "error": "Wrong data type in field title!"
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
    "message": "Partnership not found!",
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
