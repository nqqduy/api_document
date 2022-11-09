## # **Get All Top Artist**

## **API Get All Top Artist**

### **GET**

**Production**: [https://api.artnguide.co.kr/api/v1/top-artist/get-all?page=&size=&query=&startTime=&endTime=](https://api.artnguide.co.kr/api/v1/top-artist/get-all?page=&size=&query=&startTime=&endTime=)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/top-artist/get-all?page=&size=&query=&startTime=&endTime=](https://dev-api.artnguide.co.kr/api/v1/top-artist/get-all?page=&size=&query=&startTime=&endTime=)

## **REQUEST**

**Config header**:

**Data raw**

```
none
```

### **Parameter**

|   Field   | Type      | Description                                   | required         |
| :-------: | --------- | --------------------------------------------- | ---------------- |
|   page    | string    | Page number to display                        | no (default: 1)  |
|   size    | string    | Number of items displayed                     | no (default: 10) |
|   query   | string    | Overall search like title                     | no               |
| startTime | timestamp | Search the banner after the date of creation  | no               |
|  endTime  | timestamp | Search the banner before the date of creation | no               |

## **RESPONSE**

### **Success 200**

```json
{
    "result": true,
    "message": "ok",
    "data": {
        "datas": [
            {
                "id": 1,
                "rank": 1,
                "authorName": "야요이 쿠사마",
                "productName": " Pumpkin (2004)",
                "price": 1950000000,
                "tradeDay": "2022-09-27T07:00:00.000Z",
                "exhibitionDestination": "서울옥션",
                "createdAt": "2022-05-12T02:29:41.000Z",
                "updatedAt": "2022-05-12T02:29:41.000Z"
            },
            {
                "id": 2,
                "rank": 2,
                "authorName": "박수근",
                "productName": "노상 (1962)",
                "price": 800000000,
                "tradeDay": "2022-09-27T07:00:00.000Z",
                "exhibitionDestination": "서울옥션",
                "createdAt": "2022-05-12T02:31:18.000Z",
                "updatedAt": "2022-05-12T02:31:18.000Z"
            },
            {
                "id": 3,
                "rank": 3,
                "authorName": "박서보",
                "productName": "묘법 No.941120",
                "price": 530000000,
                "tradeDay": "2022-09-27T07:00:00.000Z",
                "exhibitionDestination": "서울옥션",
                "createdAt": "2022-05-12T02:32:41.000Z",
                "updatedAt": "2022-05-12T02:32:41.000Z"
            },
            {
                "id": 4,
                "rank": 4,
                "authorName": "유영국",
                "productName": "Mountain",
                "price": 410000000,
                "tradeDay": "2022-09-27T07:00:00.000Z",
                "exhibitionDestination": "서울옥션",
                "createdAt": "2022-05-12T02:33:32.000Z",
                "updatedAt": "2022-05-12T02:33:32.000Z"
            },
            {
                "id": 6,
                "rank": 5,
                "authorName": "정상화",
                "productName": "Untitled 013-11-20",
                "price": 360000000,
                "tradeDay": "2022-09-28T07:00:00.000Z",
                "exhibitionDestination": "케이옥션",
                "createdAt": "2022-05-16T07:17:03.000Z",
                "updatedAt": "2022-05-16T07:17:03.000Z"
            },
            {
                "id": 7,
                "rank": 6,
                "authorName": "김환기",
                "productName": "무제",
                "price": 350000000,
                "tradeDay": "2022-09-27T07:00:00.000Z",
                "exhibitionDestination": "서울옥션",
                "createdAt": "2022-05-16T07:18:01.000Z",
                "updatedAt": "2022-05-16T07:18:01.000Z"
            },
            {
                "id": 8,
                "rank": 7,
                "authorName": "이배",
                "productName": "불로부터 ",
                "price": 290000000,
                "tradeDay": "2022-09-28T07:00:00.000Z",
                "exhibitionDestination": "케이옥션",
                "createdAt": "2022-05-16T07:22:33.000Z",
                "updatedAt": "2022-05-16T07:22:33.000Z"
            },
            {
                "id": 11,
                "rank": 8,
                "authorName": "이우환",
                "productName": "바람과 함께",
                "price": 280000000,
                "tradeDay": "2022-09-28T07:00:00.000Z",
                "exhibitionDestination": "케이옥션",
                "createdAt": "2022-05-16T09:14:32.000Z",
                "updatedAt": "2022-05-16T09:14:32.000Z"
            },
            {
                "id": 16,
                "rank": 9,
                "authorName": "이중섭",
                "productName": "아이들과 물고기와 게",
                "price": 260000000,
                "tradeDay": "2022-09-28T07:00:00.000Z",
                "exhibitionDestination": "케이옥션",
                "createdAt": "2022-05-25T07:02:33.000Z",
                "updatedAt": "2022-05-25T07:02:33.000Z"
            },
            {
                "id": 17,
                "rank": 10,
                "authorName": "에드가 플랜스",
                "productName": "Artist Girl Imagination Flies Across the Blue Sky",
                "price": 250000000,
                "tradeDay": "2022-09-27T07:00:00.000Z",
                "exhibitionDestination": "서울옥션",
                "createdAt": "2022-05-26T04:43:29.000Z",
                "updatedAt": "2022-05-26T04:43:29.000Z"
            }
        ],
        "pageable": {
            "totalElement": 10,
            "currentElement": 10,
            "totalPage": 1,
            "page": 1,
            "size": 10,
            "hasNext": false
        }
    }
}
```

### **ERROR 400 (Bad Request)**

```json
{
    "errorCode": "invalid_data",
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
