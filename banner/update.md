## # **Update Banner**

## **API Update Banner**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/banner/update](https://api.artnguide.co.kr/api/v1/banner/update)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/banner/update](https://dev-api.artnguide.co.kr/api/v1/banner/update)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

Authorization: "bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"

**Data raw**

```json
{
    "bannerId": 23,
    "title": "기존 안드로이드 앱은 사용할 수 없나요?",
    "description": "",
    "btnText": "apply",
    "redirectUrl": "https://www.redirect-url/myUrl",
    "bgUrl": "https://www.background/myUrl",
    "textColorHex": "#FF0000",
    "displayOrder": 1
}
```

### **Parameter**

|     Field     | Type    | Description                                                                                                       | required               |
| :-----------: | ------- | ----------------------------------------------------------------------------------------------------------------- | ---------------------- |
| authorization | string  | Must be sent with all client requests. This Token helps server to validate request source. Provided by ARTNGUIDE. | yes                    |
|   bannerId    | integer | Banner id                                                                                                         | yes                    |
|     title     | string  | Banner title                                                                                                      | yes                    |
|  description  | string  | Banner description                                                                                                | yes                    |
|  redirectUrl  | string  | Redirect url when clicked                                                                                         | yes                    |
|     bgUrl     | string  | Background url                                                                                                    | yes                    |
| textColorHex  | string  | Color code for text                                                                                               | yes (default: #ffffff) |
|     icon      | string  | add icon for FAQ                                                                                                  | yes                    |
| displayOrder  | integer | Display order                                                                                                     | yes                    |

## **RESPONSE**

### **Success 200**

```json
{
    "result": true,
    "message": "Update banner successfully!",
    "data": null
}
```

### **ERROR 400 (Bad Request)**

```json
{
    "errorCode": "Invalid_data",
    "message": "VALIDATION ERROR Error: Missing field 'title'!",
    "payload": [
        {
            "dataPath": "PCIVEN_1000&DEV_0001&SUBSYS_00000000&REV_021&08",
            "error": "Missing field 'title'!"
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
    "message": "Banner not found!",
    "data": null,
    "errorCode": "banner_404"
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
