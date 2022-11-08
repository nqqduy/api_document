## # **Upload File**

## **API Upload File**

### **POST**

**Production**: [https://api.artnguide.co.kr/api/v1/upload/single-file](https://api.artnguide.co.kr/api/v1/upload/single-file)

**Test**: [https://dev-api.artnguide.co.kr/api/v1/upload/single-file](https://dev-api.artnguide.co.kr/api/v1/upload/single-file)

## **REQUEST**

**Config header**:

Content-Type: "application/json"

**Data raw**

```json
none
```

### **Parameter**

|  Field   | Type   | Description           | required |
| :------: | ------ | --------------------- | -------- |
|   file   | file   | image                 | yes      |
| category | string | folder to save images | no       |

## **RESPONSE**

### **Success 200**

```json
{
    "ETag": "\"8afd5af6cf85f4e1321b94f328a1680b\"",
    "Location": "https://artnguide.s3.ap-northeast-2.amazonaws.com/etc/artng_1667902643565_download.png",
    "key": "etc/artng_1667902643565_download.png",
    "Key": "etc/artng_1667902643565_download.png",
    "Bucket": "artnguide"
}
```

### **ERROR 404 (Not Found)**

```json
{
    "result": false,
    "errorCode": "file_not_found"
}
```

### **ERROR 500 (Internal Server Error)**

```json
{
    "errorCode": "sv_500"
}
```
