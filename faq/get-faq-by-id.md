## # **Get All FAQ**

## **API Get All FAQ**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/faq/get-all](https://api.artnguide.co.kr/api/v1/faq/get-all)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/faq/get-all](https://dev-api.artnguide.co.kr/api/v1/faq/get-all)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

Authorization: "bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"
**Data raw**

```json
{
    "page": "2",
    "size": "15",
    "query": "blockchain",
    "startTime": "2022-08-30T08:45:52.000Z",
    "endTime": "2022-09-30T08:45:52.000Z",
    "categoryCode": "CATEGORY_OF_FAQ"
}
```

title

### **Parameter**

|     Field     | Type   | Description                                        | required        |
| :-----------: | ------ | -------------------------------------------------- | --------------- |
| Authorization | string | Page number to display                             | no              |
|     page      | string | Page number to display                             | yes default(1)  |
|     size      | string | Number of items displayed                          | yes default(20) |
|     query     | string | Overall search like description, title and content | yes             |
|   startTime   | string | Search the FAQ after the date of creation          | yes             |
|    endTime    | string | Search the FAQ before the date of creation         | yes             |
| categoryCode  | string | Overall search like description, title and content | yes             |

## **RESPONSE**

### **Success 200**

```json
{
    "datas": [
        {
            "id": 99,
            "title": "기존 안드로이드 앱은 사용할 수 없나요?",
            "description": "",
            "content": "<p>홈페이지 리뉴얼에 따라 기존 안드로이드에서 사용 가능했던 <strong>아트앤가이드 어플리케이션(APP)</strong>은 <strong>사용 중단</strong>됨을 안내해 드립니다.</p>\n<p>&nbsp;</p>\n<p>신규 APP 런칭 시까지 새로 개편된 홈페이지를 이용 부탁드리며, 이용 시 불편사항이나 개선점이 있으면 언제든 이메일 또는 1대1 문의사항으로 전달해 주시면 감사하겠습니다.</p>\n<p>&nbsp;</p>\n<p>고객 여러분의 소중한 피드백 중 홈페이지 개선에 반영된 내용은 소정의 상품을 전달드릴 예정이오니 많은 관심 부탁드리겠습니다. &nbsp; &nbsp;</p>",
            "icon": "",
            "attachments": "",
            "categoryId": 4,
            "createdBy": 1,
            "updatedBy": 1,
            "isDeleted": false,
            "createdAt": "2022-08-31T04:18:56.000Z",
            "updatedAt": "2022-08-31T06:05:58.000Z",
            "active": true,
            "displayOrder": 1,
            "categoryCode": "GP",
            "categoryName": "공동구매",
            "publisher": "Admin 1",
            "categoryActive": true
        },
        {
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
            "publisher": "Admin 1",
            "categoryActive": true
        },
        {
            "id": 96,
            "title": "작품확인서를 신청했는데, 언제쯤 받을 수 있나요?",
            "description": "",
            "content": "<p>아트앤가이드 공동구매 작품확인서는 공동구매 기간인 <strong>20일이 지난 종료시점 이후, 14일 이후에 발송</strong>되고 있습니다.&nbsp;<br><br>아트앤가이드 홈페이지 공지사항에서 각 공동구매의 작품확인서 배송 진행상황을 업데이트 하고 있습니다.&nbsp;<br><br></p>",
            "icon": "",
            "attachments": "",
            "categoryId": 5,
            "createdBy": 1,
            "updatedBy": 1,
            "isDeleted": false,
            "createdAt": "2022-08-23T05:02:45.000Z",
            "updatedAt": "2022-08-23T08:48:20.000Z",
            "active": true,
            "displayOrder": 1,
            "categoryCode": "GP_SERIAL",
            "categoryName": "작품확인서",
            "publisher": "Admin 1",
            "categoryActive": true
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
        "message": "404 not found!",
        "data": null,
        "errorCode": "faq_404"
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
