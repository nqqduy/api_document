## # **Get FAQ By Id**

## **API Get FAQ By Id**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/faq/get-by-id](https://api.artnguide.co.kr/api/v1/faq/get-by-id)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/faq/get-by-id](https://dev-api.artnguide.co.kr/api/v1/faq/get-by-id)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

Authorization: "bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"
**Data raw**

```json
{
    "faqId": 2
}
```

title

### **Parameter**

|     Field     | Type    | Description            | required |
| :-----------: | ------- | ---------------------- | -------- |
| Authorization | string  | Page number to display | no       |
|     faqId     | integer | FAQ's id               | yes      |

## **RESPONSE**

### **Success 200**

```json
{
    "result": true,
    "message": "Get successfully!",
    "data": {
        "id": 97,
        "title": "공동구매 총결제금액보다 더 많이 입금했어요. 어떻게 환불 받나요?",
        "description": "",
        "content": "<p>공동구매 참여시 최종 결제 금액보다 추가금액으로 입금하신 경우,&nbsp;</p>\n<p><span style=\"text-decoration: underline;\"><strong>차주 월~화요일 </strong>사이에 <strong>주문서상에 작성하신 계좌정보</strong>로</span> 추가입금 하신 금액이 환불 처리 됩니다.&nbsp;</p>",
        "icon": "",
        "attachments": "",
        "categoryId": 4,
        "createdBy": 1,
        "updatedBy": 1,
        "isDeleted": false,
        "createdAt": "2022-08-23T08:41:24.000Z",
        "updatedAt": "2022-08-23T08:47:00.000Z",
        "active": true,
        "displayOrder": 1,
        "categoryCode": "GP",
        "categoryName": "공동구매",
        "publisher": "Admin 1"
    }
}
```

### **ERROR 400 (Bad Request)**

```json
{
    "errorCode": "Invalid_data",
    "message": "VALIDATION ERROR Error: Wrong data in field 'faqId'!",
    "payload": [
        {
            "dataPath": "/faqId",
            "error": "Wrong data in field 'faqId'!"
        }
    ]
}
```

### **ERROR 404 (Not Found)**

```json
{
    "result": false,
    "message": "Faq not found!",
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
