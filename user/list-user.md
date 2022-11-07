## # **List User**

## **API List User**

### **GET**

**Production**: [https://api.artnguide.co.kr/api/v1/user/list-user?size=&page=&userId=&gender=&querySearch=&userRole=&leave=&requestLeave&active](https://api.artnguide.co.kr/api/v1/user/list-user?size=&page=&userId=&gender=&querySearch=&userRole=&leave=&requestLeave&active)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/user/list-user?size=&page=&userId=&gender=&querySearch=&userRole=&leave=&requestLeave&active](https://dev-api.artnguide.co.kr/api/v1/user/list-user?size=&page=&userId=&gender=&querySearch=&userRole=&leave=&requestLeave&active)

## **REQUEST**

**Config header**:

Authorization: "bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"

**Data raw**

```json
none
```

### **Parameter**

userId=&gender=&querySearch=&userRole=&leave=&requestLeave&active
| Field | Type | Description | required |
| :-----------: | ------ | ----------------------------------------------------------------------------------------------------------------- | --------------- |
| id | string | User's id | yes |
| authorization | string | Must be sent with all client requests. This Token helps server to validate request source. Provided by ARTNGUIDE. | yes |
| page | string | page order of display. | No (default: 1) |
| size | string | number of items displayed on 1 page. | No (default: 20) |
| userId | string | User's id | No |
| gender | string | User's gender | No |
| querySearch | string | query Search | No |
| userRole | string | User's role | No |
| leave | boolean | The user left | No |
| requestLeave | boolean | The user asked to leave | No |
| active | boolean | Active account | No |

## **RESPONSE**

### **Success 200**

```json
{
    "data": {
        "result": true,
        "message": "ok!",
        "datas": [
            {
                "userId": 123,
                "userUserName": "duy nguyen",
                "userEmail": "duynguyen@gmail.com",
                "userUserName": "duynguyen",
                "userDisplayName": "garen",
                "userAvatar": "https://aws.s3/useravatar",
                "userSnsId": "abn123",
                "userGender": "male",
                "userAccountType": "normal",
                "userUserRole": "USER",
                "userCreateTime": "2017-01-30 16:49:19",
                "userUpdateTime": "2017-01-30 16:49:19",
                "userLastLogin": "10/15/1997",
                "userEmailReceive": true,
                "userSmsReceive": false,
                "userPoint": 120,
                "userLoginCount": 1,
                "userLeave": false,
                "userIsDelete": false,
                "userBirthDate": "10-15-1997",
                "userAuthVerified": false,
                "userVerifiedPhoneNumber": null,
                "userPwEncryptMethod": "NEW",
                "userIdOriginArtnguide": null,
                "userCloneOfUid": null,
                "userRequestLeave": false,
                "userRequestLeaveAt": null,
                "userNeedMigration": false,
                "userOldPhoneNumber": "+84987438145",
                "userAdminNote": "nothing",
                "userVerifiedAt": null,
                "userRegisteredAt": "2017-01-30 16:49:19 ",
                "biPhoneNumber": "+84021566478",
                "biBankAccount": "6532108745765",
                "biBankHolderName": "Duy Nguyen",
                "biBankName": "VIETCOMBNK",
                "uciCompanyBc": "21321054",
                "uciCompanyBlUrl": "https://aws.s3/url",
                "uciCompanyName": "AIDEAVN",
                "uciCompanyCeo": "Duy Nguyen"
            }
        ],
        "pageable": {
            "totalElement": 20,
            "currentElement": 1,
            "totalPage": 4,
            "page": 1,
            "size": 5,
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
            "dataPath": "PCIVEN_1000&DEV_0001&SUBSYS_00000000&REV_02\1&08",
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
    "data": {
        "result": false,
        "message": "Result not found!",
        "data": null,
        "errorCode": "user_404"
    }
}
```

### **ERROR 500 (Internal Server Error)**

```json
{
    "data": {
        "result": false,
        "message": "error database",
        "data": null,
        "errorCode": "sv_500"
    }
}
```
