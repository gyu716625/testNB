---
description: '유저의 email , 아이템에 관한 API 정보를 제공합니다.'
---

# Info

{% api-method method="get" host="http://13.125.237.84:5000" path="/info" %}
{% api-method-summary %}
Info
{% endapi-method-summary %}

{% api-method-description %}
 이 엔드포인트에서는 User의 email과 Item들에 대한 모든 정보를 담아서 응답합니다.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="token" type="string" required=true %}
Authentication token to track down who is emptying our stocks.
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
 데이터 응답 성공   
{% endapi-method-response-example-description %}

```
{ "data": [
        {
            "ItemId": 1,
            "image": "image_url",
            "category": "cloth",
            "type": "pants",
            "buydate": "2007",
            "price": 45000,
            "storage": "행",
            "sp": 1,
            "sm": 0,
            "f": 0,
            "w": 1
        },
        {
            "ItemId": 2,
            "image": "image_ur",
            "category": "cloth",
            "type": "shirts",
            "buydate": "2003",
            "price": 35000,
            "storage": "서",
            "sp": 0,
            "sm": 1,
            "f": 1,
            "w": 0
        }
    ] }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}
 토큰정보를 서버에서 확인할 수 없는 경우   
{% endapi-method-response-example-description %}

```
{ "message": err.message }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
 아이템 등록에 에러가  발생한 경우  
{% endapi-method-response-example-description %}

```
{ "message": "Failed" }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=409 %}
{% api-method-response-example-description %}
 유저가  등록한 아이템이 db에 존재하지 않을 경우  
{% endapi-method-response-example-description %}

```
{ "message": "no data" }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



