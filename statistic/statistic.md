## # **Get All Popup By Admin**

## **API Get All Popup By Admin**

### **GET**

**Production**: [https://api.artnguide.co.kr/api/v1/statistic/dashboard](https://api.artnguide.co.kr/api/v1/statistic/dashboard)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/statistic/dashboard](https://dev-api.artnguide.co.kr/api/v1/statistic/dashboard)

## **REQUEST**

**Config header**:

Authorization: "bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"

**Data raw**

```
none
```

### **Parameter**

|     Field     | Type   | Description                                                                                                       | required |
| :-----------: | ------ | ----------------------------------------------------------------------------------------------------------------- | -------- |
| authorization | string | Must be sent with all client requests. This Token helps server to validate request source. Provided by ARTNGUIDE. | yes      |

## **RESPONSE**

### **Success 200**

```json
{
    "result": true,
    "message": "Get all popup successfully!",
    "data": {
        "totalUser": 10,
        "totalUserLeave": 2,
        "registerToday": 2,
        "registerYesterday": 4,
        "registerThisMonth": 3,
        "registerLastMonth": 3,
        "verifiedAccountToday": 2,
        "verifiedAccountYesterday": 3,
        "totalVerifiedAccount": 5,
        "visitedToday": 9,
        "visitedThisMonth": 100,
        "lastTimeCalc": "2022-11-09T07:42:57.527Z"
    }
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

### **ERROR 500 (Internal Server Error)**

```json
{
    "result": false,
    "message": "error database",
    "data": null,
    "errorCode": "sv_500"
}
```
