## # **User Details**

## **API User Details**

### **GET**

**Production**: [https://api.artnguide.co.kr/api/v1/user/details?id=](https://api.artnguide.co.kr/api/v1/user/details)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/user/details](https://dev-api.artnguide.co.kr/api/v1/user/details)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

Authorization: "bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"

**Data raw**

```json
none
```

### **Parameter**

|     Field     | Type   | Description                                                                                                       | required |
| :-----------: | ------ | ----------------------------------------------------------------------------------------------------------------- | -------- |
|      id       | string | User's id                                                                                                         | yes      |
| authorization | string | Must be sent with all client requests. This Token helps server to validate request source. Provided by ARTNGUIDE. | yes      |

## **RESPONSE**

### **Success 200**

```json
{
    "data": {
        "result": true,
        "message": "get success",
        "data": {
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
            "biInvoiceType": "VAT",
            "biInvoiceInfo": "invoice information",
            "biPhoneNumber": "+84021566478",
            "biZipCode": "32131",
            "biAddress": "Thu Binh District, Ho Chi Minh city",
            "biAddress2": "Thu Duc District, Ho Chi Minh city",
            "biBankAccount": "6532108745765",
            "biBankHolderName": "Duy Nguyen",
            "biBankName": "VIETCOMBNK",
            "uciCompanyBc": "21321054",
            "uciCompanyBlUrl": "https://aws.s3/url",
            "uciCompanyName": "AIDEAVN",
            "uciCompanyCeo": "Duy Nguyen",
            "uciCompanyField": "IT",
            "uciCompanyStatus": "active",
            "uciCompanyZipCode": "1500",
            "uciCompanyAddr1": "Tan Binh District, Ho Chi Minh city",
            "uciCompanyAddr2": "Thu Duc District, Ho Chi Minh city"
        }
    }
}
```

### **ERROR 400 (Bad Request)**

```json
{
    "errorCode": "Invalid_data",
    "message": "VALIDATION ERROR Error: Wrong data in field id!",
    "payload": [
        {
            "dataPath": "PCIVEN_1000&DEV_0001&SUBSYS_00000000&REV_02\1&08",
            "error": "Wrong data in field id!"
        }
    ]
}
```

### **ERROR 401 (Unauthorized Error)**

```json
{}
```

### **ERROR 404 (Not Found)**

```json
{
    "data": {
        "result": false,
        "message": "User not found!",
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
