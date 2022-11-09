## # **Find Partnership**

## **API Find Partnership**

### **GET**

**Production**: [https://api.artnguide.co.kr/api/v1/partnership/find?id=&querySearch=&size=&page=&division=&confirm=&startDate=&endDate=](https://api.artnguide.co.kr/api/v1/partnership/find?id=&querySearch=&size=&page=&division=&confirm=&startDate=&endDate=)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/partnership/find?id=&querySearch=&size=&page=&division=&confirm=&startDate=&endDate=](https://dev-api.artnguide.co.kr/api/v1/partnership/find?id=&querySearch=&size=&page=&division=&confirm=&startDate=&endDate=)

## **REQUEST**

**Config header**:

Authorization: "bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"

**Data raw**

```
none
```


### **Parameter**

|   Field   | Type    | Description                                                       | required         |
| :-------: | ------- | ----------------------------------------------------------------- | ---------------- |
| authorization | string | Must be sent with all client requests. This Token helps server to validate request source. Provided by ARTNGUIDE. | yes |
|   page    | string  | Page number to display                                            | no (default: 1)  |
|   size    | string  | Number of items displayed                                         | no (default: 20) |
|   query   | string  | Overall search like title, contact person, phone number and email | no               |
|  confirm  | boolean | Do you agree to cooperate? title!                                 | no               |
| startTime | string  | Search the article after the date of creation                     | no               |
|  endTime  | string  | Search the article before the date of creation                    | no               |

## **RESPONSE**

### **Success 200**

```json
{
    "result": true,
    "message": "ok!",
    "data": {
        "datas": [
            {
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
        ],
        "pageable": {
            "totalElement": 30,
            "currentElement": 12,
            "totalPage": 3,
            "page": 1,
            "size": 12,
            "hasNext": true
        }
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
    "message": "Result not found",
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
