## # **Get All Popup By Admin**

## **API Get All Popup By Admin**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/popup/admin-get-all](https://api.artnguide.co.kr/api/v1/popup/admin-get-all)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/popup/admin-get-all](https://dev-api.artnguide.co.kr/api/v1/popup/admin-get-all)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

Authorization: "bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"

**Data raw**

```json
{
    "page": "1",
    "size": "15",
    "query": "blockchain"
}
```

### **Parameter**

|     Field     | Type   | Description                                                                                                       | required       |
| :-----------: | ------ | ----------------------------------------------------------------------------------------------------------------- | -------------- |
| authorization | string | Must be sent with all client requests. This Token helps server to validate request source. Provided by ARTNGUIDE. | yes            |
|     page      | string | Page number to display                                                                                            | no default(1)  |
|     size      | string | Number of items displayed                                                                                         | no default(20) |
|     query     | string | Overall search like title, contents, redirect url and routes                                                      | no             |

## **RESPONSE**

### **Success 200**

```json
{
    "result": true,
    "message": "Get all popup successfully!",
    "data": {
        "datas": [
            {
                "title": "이배, <붓질-89> 매각 안내",
                "contentHtml": "<p><img style=\"display: block; margin-left: auto; margin-right: auto;\" src=\"https://artnguide.s3.ap-northeast-2.amazonaws.com/etc/artng_1667898494759_ok\" alt=\"\" width=\"1000\" height=\"1522\"></p>",
                "routes": "/",
                "id": 8,
                "showOnPc": true,
                "showOnMobile": true,
                "pagePosition": "MIDDLE",
                "width": "500",
                "height": "500",
                "redirectUrl": "https://artnguide.co.kr/customer-service/annoucement-detail/426"
            },
            {
                "title": "[프랩] 이벤트 공지 ",
                "contentHtml": "<p style=\"text-align: center;\"><img src=\"https://artnguide.s3.ap-northeast-2.amazonaws.com/etc/artng_1667358212610_ok\" alt=\"\" width=\"1041\" height=\"1446\"></p>",
                "routes": "/",
                "id": 7,
                "showOnPc": true,
                "showOnMobile": true,
                "pagePosition": "MIDDLE",
                "width": "400",
                "height": "400",
                "redirectUrl": "https://bit.ly/3FDTkTS"
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
    "message": "VALIDATION ERROR Error: Wrong data in field page!",
    "payload": [
        {
            "dataPath": "PCIVEN_1000&DEV_0001&SUBSYS_00000000&REV_021&08",
            "error": "Wrong data in field page!"
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
    "errorCode": "popup_404"
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
