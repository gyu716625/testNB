---
description: 이미지 파일을 url로 변환 시켜주는 어'쩌구
---

# Image

{% api-method method="post" host="http://54.180.149.177:5000" path="/image/upload" %}
{% api-method-summary %}
Get Image Url
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to get free cakes.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-form-data-parameters %}
{% api-method-parameter name="image" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
S3에 이미지가 성공적으로 업로드 됐을 때, 
{% endapi-method-response-example-description %}

```
{    "imageUrl": "url 주소"    }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
 응답이 실패했을  때,  
{% endapi-method-response-example-description %}

```
{    "message": err.message    }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



