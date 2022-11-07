## # **Update User Information By Admin**

## **API Update User Information By Admin**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/user/admin-update-user-info](https://api.artnguide.co.kr/api/v1/user/admin-update-user-info)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/user/admin-update-user-info](https://dev-api.artnguide.co.kr/api/v1/user/admin-update-user-info)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

Authorization: "bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"

**Data raw**

```json
{
    "id": 123,
    "displayName": "duynguyen5",
    "email": "duynguyen@gmail.com",
    "phoneNumber": "+840987456123",
    "avatar": "http://www.aws.s3/myAvatar",
    "smsReceive": true,
    "emailReceive": true,
    "biZipCode": "123321",
    "biAddress": "Tan Binh district, Ho Chi Minh city",
    "biAddress2": "Thu Duc district, Ho Chi Minh city",
    "biBankAccount": "0320320.0",
    "biBankHolderName": "ARTNGUIDE",
    "biBankName": "VIETCOMBANK",
    "birthDate": "12-05-2000",
    "companyBc": "65512121",
    "companyCEO": "faker",
    "companyZipCode": "21321",
    "companyField": "IT",
    "companyAddress": "Tan Binh district, Ho Chi Minh city",
    "companyAddress2":  "Thu Duc district, Ho Chi Minh city",,
    "companyStatus": "active",
    "companyBlUrl": "https://www.hdhd.com/myBlURL",
    "companyName": "AIDEAVN",
    "invoiceInfo": "invoiceInfo",
    "adminNote": "adminNote"
}
```

### **Parameter**

|      Field       | Type    | Description                                                                                                       | required |
| :--------------: | ------- | ----------------------------------------------------------------------------------------------------------------- | -------- |
|      userId      | integer | User's id                                                                                                         | yes      |
|  authorization   | string  | Must be sent with all client requests. This Token helps server to validate request source. Provided by ARTNGUIDE. | yes      |
|    adminNote     | string  | Note of admin                                                                                                     | no       |
|      avatar      | string  | User's avatar                                                                                                     | no       |
|   displayName    | string  | User's display name                                                                                               | no       |
|      email       | string  | User's email                                                                                                      | no       |
|   phoneNumber    | string  | User's phone number                                                                                               | no       |
|    smsReceive    | boolean | smsReceive                                                                                                        | no       |
|   emailReceive   | boolean | User's display name                                                                                               | no       |
|    biZipCode     | string  | zip code                                                                                                          | no       |
|    biAddress     | string  | Buyer address                                                                                                     | no       |
|    biAddress2    | string  | Buyer address 2                                                                                                   | no       |
|  biBankAccount   | string  | Buyer bank account                                                                                                | no       |
| biBankHolderName | string  | Buyer bank holder name                                                                                            | no       |
|    biBankName    | string  | Buyer bank name                                                                                                   | no       |
|    birthDate     | date    | Buyer birthDate                                                                                                   | no       |
|    companyBc     | string  | Company bussiness code                                                                                            | no       |
|    companyCEO    | string  | Company CEO name                                                                                                  | no       |
|  companyZipCode  | string  | Company Zip Code                                                                                                  | no       |
|   companyField   | string  | Company Field                                                                                                     | no       |
|  companyAddress  | string  | Company Address                                                                                                   | no       |
| companyAddress2  | string  | Company Address 2                                                                                                 | no       |
|  companyStatus   | string  | Company status                                                                                                    | no       |
|   companyBlUrl   | string  | Company bussiness registration url                                                                                | no       |
|   companyName    | string  | Company name                                                                                                      | no       |
|   invoiceInfo    | string  | Invoice Infomation                                                                                                | no       |

## **RESPONSE**

### **Success 200**

```json
{
    "data": {
        "result": true,
        "message": "Update information ok!",
        "datas": null
    }
}
```

### **ERROR 400 (Bad Request)**

```json
{
    "errorCode": "Invalid_data",
    "message": "VALIDATION ERROR Error: wrong data in field userId",
    "payload": [
        {
            "dataPath": "PCIVEN_1000&DEV_0001&SUBSYS_00000000&REV_02\1&08",
            "error": "wrong data in field userId"
        }
    ]
}
```

### **ERROR 401 (Unauthorized Error)**

```json
{}
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

```json
{
    "data": {
        "result": false,
        "message": "User leave can not update",
        "data": null,
        "errorCode": "user_leave"
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
