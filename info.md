---
description: '유저의 email , 아이템에 관한 API 정보를 제공합니다.(나중에 수정)'
---

# Info

{% api-method method="get" host="{baseUrl}" path="/info" %}
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
 데이터 응답 성
{% endapi-method-response-example-description %}

```
{}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
 데이터 응답 실 
{% endapi-method-response-example-description %}

```
{    "message": "Failed" }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



