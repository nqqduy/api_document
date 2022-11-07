## # **Sign Up**

## **API Sign Up**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/auth/sign-up](https://api.artnguide.co.kr/api/v1/auth/sign-up)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/auth/sign-up](https://dev-api.artnguide.co.kr/api/v1/auth/sign-up)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

**Data raw**

```json
{
  "username": "antnguide",
  "email": "antnguide@gmail.com",
  "password": "antnguide",
  "gender": "MALE",
  "birthDate": "02/20/2022",
  "joinType": "NORMAL",
  "smsReceive": true,
  "snsId": "antnguide",
  "phone": "0987456123",
  "address1": "Tan Binh ward, Ho Chi Minh city, Viet Nam",
  "address2": "Tan Phu ward, Ho Chi Minh city, Viet Nam",
  "zipCode": "008428",
  "bankName": "LG",
  "bankAccount": "antnguide",
  "bankHolderName": "antnguide",
  "bankHolderName": "antnguide",
  "invoiceType": "ENTERPRISE_TAX",
  "invoiceInfo": "invoice Info"
}
```

### **Parameter**

|     Field      | Type   | Description                            | required |
| :------------: | ------ | -------------------------------------- | -------- |
|    userName    | string | User's username                        | yes      |
|     email      | string | User's email                           | yes      |
|    password    | string | User's password                        | yes      |
|     phone      | string | User phone                             | yes      |
|     gender     | string | User's gender (**default: male**)      |          |
|   birthDate    | string | User's birthdate                       |          |
|    joinType    | string | Join type                              |          |
|   smsReceive   | string | smsReceive                             |          |
|     snsId      | string | snsId                                  |          |
|    userRole    | string | User role (enum: ADMIN, COMPANY, USER) |          |
|    address1    | string | address1                               |          |
|    address2    | string | address2                               |          |
|    zipCode     | string | zipCode                                |          |
|    bankName    | string | Bank Name                              |          |
|  bankAccount   | string | Bank Account                           |          |
| bankHolderName | string | Bank Holder Name                       |          |
|  invoiceType   | string | Invoice type                           |          |
|  invoiceInfo   | string | Invoice Info                           |          |

## **RESPONSE**

### **Success 200**

```json
{
  "data": {
    "result": true,
    "message": "Sign up successfully!",
    "data": null
  }
}
```

### **ERROR 400 (Bad Request)**

```json
{
  "errorCode": "Invalid_data",
  "message": "VALIDATION ERROR Error: userName is required!",
  "payload": [
    {
      "dataPath": "PCIVEN_1000&DEV_0001&SUBSYS_00000000&REV_02\1&08",
      "error": "userName is required!"
    }
  ]
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
