## # **Get All Banner**

## **API Get All Banner**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/banner/get-all](https://api.artnguide.co.kr/api/v1/banner/get-all)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/banner/get-all](https://dev-api.artnguide.co.kr/api/v1/banner/get-all)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

**Data raw**

```json
{
    "page": "2",
    "size": "15",
    "query": "blockchain",
    "startTime": "2022-08-30T08:45:52.000Z",
    "endTime": "2022-09-30T08:45:52.000Z"
}
```

### **Parameter**

|   Field   | Type      | Description                                   | required          |
| :-------: | --------- | --------------------------------------------- | ----------------- |
|   page    | string    | Page number to display                        | yes (default: 1)  |
|   size    | string    | Number of items displayed                     | yes (default: 15) |
|   query   | string    | Overall search like title                     | yes               |
| startTime | timestamp | Search the banner after the date of creation  | yes               |
|  endTime  | timestamp | Search the banner before the date of creation | yes               |

## **RESPONSE**

### **Success 200**

```json
{
    "datas": [
        {
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
    ],
    "pageable": {
        "totalElement": 22,
        "currentElement": 10,
        "totalPage": 3,
        "page": 1,
        "size": 3,
        "hasNext": true
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

### **ERROR 404 (Not Found)**

```json
{
    "code": 404,
    "data": {
        "result": false,
        "message": "No banner found!",
        "data": null,
        "errorCode": null
    }
}
```

### **ERROR 500 (Internal Server Error)**

```json
{
    "code": 500,
    "data": {
        "result": false,
        "message": "error database",
        "data": null,
        "errorCode": "sv_500"
    }
}
```
