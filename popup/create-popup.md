## # **Create Popup**

## **API Create Popup**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/popup/create](https://api.artnguide.co.kr/api/v1/popup/create)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/popup/create](https://dev-api.artnguide.co.kr/api/v1/popup/create)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

Authorization: "bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"

**Data raw**

```json
{
    "title": "리뉴얼 홈페이지 이용안내",
    "contentHtml": "<p><img src=\"https://artnguide.s3.ap-northeast-2.amazonaws.com/etc/artng_1663149004505_ok\"></p>",
    "redirectUrl": "https://artnguide.co.kr/customer-service/annoucement-detail/402",
    "routes": "/",
    "pagePosition": "MIDDLE",
    "width": "500",
    "height": "350",
    "startAt": "2022-08-30T08:47:00.000Z",
    "endAt": "2022-09-30T08:43:40.000Z",
    "showOnPc": true,
    "showOnMobile": true
}
```

### **Parameter**

|     Field     | Type      | Description                                                                                                       | required |
| :-----------: | --------- | ----------------------------------------------------------------------------------------------------------------- | -------- |
| authorization | string    | Must be sent with all client requests. This Token helps server to validate request source. Provided by ARTNGUIDE. | yes      |
|     title     | string    | Popup's title                                                                                                     | yes      |
|  contentHtml  | string    | Html code                                                                                                         | yes      |
|  redirectUrl  | string    | Redirect url when clicked                                                                                  | yes      |
|    routes     | string    | which routes will show popup                                                                                      | yes      |
| pagePosition  | string    | where the popup appears on the page                                                                               | yes      |
|     width     | string    | Popup width                                                                                                       | yes      |
|    height     | string    | Popup height                                                                                                      | yes      |
|    startAt    | timestamp | Popup start time                                                                                                  | yes      |
|     endAt     | timestamp | Popup end time                                                                                                    | yes      |

## **RESPONSE**

### **Success 200**

```json
{
    "result": true,
    "message": "Create popup successfully!",
    "data": {
        "id": 3,
        "title": "리뉴얼 홈페이지 이용안내",
        "contentHtml": "<p><img src=\"https://artnguide.s3.ap-northeast-2.amazonaws.com/etc/artng_1663149004505_ok\"></p>",
        "redirectUrl": "https://artnguide.co.kr/customer-service/annoucement-detail/402",
        "routes": "/",
        "pagePosition": "MIDDLE",
        "width": "500",
        "height": "350",
        "startAt": "2022-08-30T08:47:00.000Z",
        "endAt": "2022-09-30T08:43:40.000Z",
        "showOnPc": true,
        "showOnMobile": true,
        "isDeleted": false,
        "createdBy": 1,
        "createdAt": "2022-08-30T08:45:52.000Z",
        "updatedAt": "2022-09-14T09:50:07.000Z"
    }
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

### **ERROR 406 (Not Acceptable)**

```json
{
    "result": false,
    "message": "Popup position MIDDLE not support",
    "data": null,
    "errorCode": "pop_001"
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
