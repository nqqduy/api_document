## # **Get All Shipping Company**

## **API Get All Shipping Company**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/shipping-company/get-all](https://api.artnguide.co.kr/api/v1/shipping-company/get-all)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/shipping-company/get-all](https://dev-api.artnguide.co.kr/api/v1/shipping-company/get-all)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

**Data raw**

```json
{
    "page": "1",
    "size": "15",
    "query": "blockchain",
    "startTime": "2022-09-30T08:43:40.000Z",
    "endTime": "2022-09-30T08:43:40.000Z"
}
```

### **Parameter**

|   Field   | Type      | Description                                             | required          |
| :-------: | --------- | ------------------------------------------------------- | ----------------- |
|   page    | string    | Page number to display                                  | yes (default: 1)  |
|   size    | string    | Number of items displayed                               | yes (default: 15) |
|   query   | string    | Overall search like name                                | yes               |
| startTime | timestamp | Search the shipping company after the date of creation  | yes               |
|  endTime  | timestamp | Search the shipping company before the date of creation | yes               |

## **RESPONSE**

### **Success 200**

```json
{
    "datas": [
        {
            "id": 2,
            "trackingUrl": "https://www.tracking-url/2",
            "phone": "+840985489234",
            "displayOrder": 1,
            "createdBy": "2022-09-30T08:43:40.000Z",
            "updated_by": "2022-09-30T08:43:40.000Z",
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
        "message": "No data found!",
        "data": null,
        "errorCode": "ship_404"
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
