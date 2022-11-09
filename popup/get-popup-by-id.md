## # **Get Popup By Id**

## **API Get Popup By Id**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/popup/get-by-id](https://api.artnguide.co.kr/api/v1/popup/get-by-id)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/popup/get-by-id](https://dev-api.artnguide.co.kr/api/v1/popup/get-by-id)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

**Data raw**

```json
{
    "popupId": 1
}
```

### **Parameter**

|  Field  | Type    | Description | required |
| :-----: | ------- | ----------- | -------- |
| popupId | integer | Popup's id  | yes      |

## **RESPONSE**

### **Success 200**

```json
{
    "result": true,
    "message": "Get Popup successfully!",
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
    "message": "VALIDATION ERROR Error: Missing field 'popupId'!",
    "payload": [
        {
            "dataPath": "PCIVEN_1000&DEV_0001&SUBSYS_00000000&REV_021&08",
            "error": "Missing field 'popupId'!"
        }
    ]
}
```

### **ERROR 404 (Not Found)**

```json
{
    "result": false,
    "message": "Popup not found!",
    "data": null,
    "errorCode": "pop_404"
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
