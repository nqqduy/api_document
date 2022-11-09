## # **Get All Popup**

## **API Get All Popup**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/popup/get-all](https://api.artnguide.co.kr/api/v1/popup/get-all)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/popup/get-all](https://dev-api.artnguide.co.kr/api/v1/popup/get-all)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

**Data raw**

```json
{
    "page": "1",
    "size": "15",
    "query": "blockchain"
}
```

### **Parameter**

| Field | Type   | Description               | required       |
| :---: | ------ | ------------------------- | -------------- |
| page  | string | Page number to display    | no default(1)  |
| size  | string | Number of items displayed | no default(20) |
| query | string | Overall search            | no             |

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
        ]
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

### **ERROR 500 (Internal Server Error)**

```json
{
    "result": false,
    "message": "error database",
    "data": null,
    "errorCode": "sv_500"
}
```
