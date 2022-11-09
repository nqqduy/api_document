## # **Get Banner By Id**

## **API Get Banner By Id**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/banner/get-by-id](https://api.artnguide.co.kr/api/v1/banner/get-by-id)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/banner/get-by-id](https://dev-api.artnguide.co.kr/api/v1/banner/get-by-id)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

**Data raw**

```json
{
    "bannerId": 2
}
```

title

### **Parameter**

|  Field   | Type    | Description | required |
| :------: | ------- | ----------- | -------- |
| bannerId | integer | Banner's id | yes      |

## **RESPONSE**

### **Success 200**

```json
{
    "result": true,
    "message": "Get banner successfully!",
    "data": {
        "id": 99,
        "title": "기존 안드로이드 앱은 사용할 수 없나요?",
        "description": "",
        "btnText": "apply",
        "redirectUrl": "https://www.redirect-url/myUrl",
        "bgUrl": "https://www.background/myUrl",
        "textColorHex": "#FF0000",
        "displayOrder": 1,
        "createdBy": "2022-08-30T08:45:52.000Z",
        "updateBy": "2022-08-30T08:45:52.000Z",
        "isDeleted": false
    }
}
```

### **ERROR 400 (Bad Request)**

```json
{
    "errorCode": "Invalid_data",
    "message": "VALIDATION ERROR Error: Missing field 'bannerId'!",
    "payload": [
        {
            "dataPath": "/faqId",
            "error": "Missing field 'bannerId'!"
        }
    ]
}
```

### **ERROR 404 (Not Found)**

```json
{
    "result": false,
    "message": "Banner not found!",
    "data": null,
    "errorCode": "faq_404"
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
