---
description: '유저의 아이템 등록 , 수정, 삭제에 관한 API 정보를 제공합니다.'
---

# Item

{% api-method method="post" host="http://15.165.197.67:5000" path="/item" %}
{% api-method-summary %}
Add Item
{% endapi-method-summary %}

{% api-method-description %}
이 엔드포인트에서는 아이템을 등록합니다. 
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="token" type="string" required=true %}
Authentication token to track down who is emptying our stocks.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="season" type="array" required=true %}
ex\) season : \[sp, sm, f, w \]
{% endapi-method-parameter %}

{% api-method-parameter name="image" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="type" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="category" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="buydate" type="string" required=false %}
 입력 데이터가 없을 시 null 
{% endapi-method-parameter %}

{% api-method-parameter name="price" type="number" required=false %}
 입력데이터가 없을 시 null 
{% endapi-method-parameter %}

{% api-method-parameter name="brand" type="string" required=false %}
 입력 데이터가 없을 시 null  
{% endapi-method-parameter %}

{% api-method-parameter name="storage" type="string" required=false %}
 입력 데이터가 없을 시 null  
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
 아이템 등록 성공   
{% endapi-method-response-example-description %}

```
{    "message": "Successful",    "item_id": 44 }
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
 아이템 등록 실패      
{% endapi-method-response-example-description %}

```
{    "message": "Failed"    }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="patch" host="http://15.165.197.67:5000" path="/item/:item\_id" %}
{% api-method-summary %}
Update Item
{% endapi-method-summary %}

{% api-method-description %}
 이 엔드포인트에서는 아이템을 수정합니다.  변경하고자 하는 데이터 정보가 필요합니다.  
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="item\_id" type="integer" required=true %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="token" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="season" type="array" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="image" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="type" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="category" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="buydate" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="price" type="number" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="brand" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="storage" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
 아이템 수정 성공   
{% endapi-method-response-example-description %}

```
{ "message": "Successful update item data with season" }
or
{ "message": "Successful update item data" }
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
 아이템 수정 실패
{% endapi-method-response-example-description %}

```
{"message": "Failed"}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="delete" host="http://15.165.197.67:5000" path="/item/:item\_id" %}
{% api-method-summary %}
Delete Item
{% endapi-method-summary %}

{% api-method-description %}
이 엔드포인트에서는 아이템을 삭제합니다.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="item\_id" type="integer" required=true %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="token" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
 아이템 삭제 성공
{% endapi-method-response-example-description %}

```
{ "message": "Successful" }
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
 아이템 삭제 실패 
{% endapi-method-response-example-description %}

```
{ "message": "Failed" }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



