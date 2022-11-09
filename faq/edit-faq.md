## # **Edit FAQ**

## **API Edit FAQ**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/faq/create](https://api.artnguide.co.kr/api/v1/faq/create)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/faq/create](https://dev-api.artnguide.co.kr/api/v1/faq/create)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

Authorization: "bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"

**Data raw**

```json
{
    "faqId": 97,
    "title": "기존 안드로이드 앱은 사용할 수 없나요?",
    "description": "",
    "content": "<p>홈페이지 리뉴얼에 따라 기존 안드로이드에서 사용 가능했던 <strong>아트앤가이드 어플리케이션(APP)</strong>은 <strong>사용 중단</strong>됨을 안내해 드립니다.</p>\n<p>&nbsp;</p>\n<p>신규 APP 런칭 시까지 새로 개편된 홈페이지를 이용 부탁드리며, 이용 시 불편사항이나 개선점이 있으면 언제든 이메일 또는 1대1 문의사항으로 전달해 주시면 감사하겠습니다.</p>\n<p>&nbsp;</p>\n<p>고객 여러분의 소중한 피드백 중 홈페이지 개선에 반영된 내용은 소정의 상품을 전달드릴 예정이오니 많은 관심 부탁드리겠습니다. &nbsp; &nbsp;</p>",
    "attachments": "",
    "categoryId": 4,
    "icon": "",
    "active": true
}
```

### **Parameter**

|     Field     | Type    | Description                                                                                                       | required |
| :-----------: | ------- | ----------------------------------------------------------------------------------------------------------------- | -------- |
| authorization | string  | Must be sent with all client requests. This Token helps server to validate request source. Provided by ARTNGUIDE. | yes      |
|     faqId     | integer | FAQ's id                                                                                                          | yes      |
|     title     | string  | FAQ's title                                                                                                       | yes      |
|  description  | string  | FAQ's description                                                                                                 | yes      |
|    content    | string  | FAQ's content                                                                                                     | yes      |
|  attachments  | string  | Attach more infomation                                                                                            | yes      |
|  categoryId   | integer | FAQ category id                                                                                                   | yes      |
|     icon      | string  | add icon for FAQ                                                                                                  | yes      |
|    active     | boolean | Is it activated or not?                                                                                           | yes      |

## **RESPONSE**

### **Success 200**

```json
{
    "result": true,
    "message": "Edit successfully!",
    "data": null
}
```

### **ERROR 400 (Bad Request)**

```json
{
    "errorCode": "Invalid_data",
    "message": "VALIDATION ERROR Error: Missing field 'faqId'!",
    "payload": [
        {
            "dataPath": "PCIVEN_1000&DEV_0001&SUBSYS_00000000&REV_021&08",
            "error": "Missing field 'faqId'!"
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
    "result": false,
    "message": "Category not found!",
    "data": null,
    "errorCode": "faq_c_404"
}
```

```json
{
    "result": false,
    "message": "faq_category",
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
