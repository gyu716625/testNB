---
description: '유저의 회원가입 , 로그인, 비밀번호 변경, 회원탈퇴에 관한 API 정보를 제공합니다.'
---

# User

{% api-method method="post" host="http://54.180.149.177:5000" path="/user/signup" %}
{% api-method-summary %}
SignUp
{% endapi-method-summary %}

{% api-method-description %}
 회원가입 용 엔드포인트로 email, password를 데이터로 받습니다. 
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="email" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="password" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
 회원가입 성공
{% endapi-method-response-example-description %}

```
{ "message": "Successful" }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=409 %}
{% api-method-response-example-description %}
 이미 존재하는 이메일을 입력
{% endapi-method-response-example-description %}

```
{ "message": "Already exists" }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="http://54.180.149.177:5000" path="/user/signin" %}
{% api-method-summary %}
SignIn
{% endapi-method-summary %}

{% api-method-description %}
로그인 용 엔드포인트로 email, password를 데이터 받습니다.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="email" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="password" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
 로그인 성공
{% endapi-method-response-example-description %}

```
{ "message": "Successful", "id": 1, "token": "user's token value" }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
 존재하지 않는 유저   
{% endapi-method-response-example-description %}

```
{"message": "unvalid user"}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="http://54.180.149.177:5000" path="/user/newpwd" %}
{% api-method-summary %}
Change Password
{% endapi-method-summary %}

{% api-method-description %}
 비밀번호 변경을 위한 엔드포인트로 password와 newpassword 받습니다.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="token" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="newpassword" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="password" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
 패스워드 변경 성공  
{% endapi-method-response-example-description %}

```
{ "message": "Successful" }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
 패스워드 변경 실패  
{% endapi-method-response-example-description %}

```
{"message": "Failed" }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=409 %}
{% api-method-response-example-description %}
 일치하지 않는 패스워드를 입력 
{% endapi-method-response-example-description %}

```
{ "message": "Wrong Password" }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="http://54.180.149.177:5000" path="/user/signout" %}
{% api-method-summary %}
Signout
{% endapi-method-summary %}

{% api-method-description %}
 로그아웃을 위한 엔드 포인트 입니다.  
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="token" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
 로그아웃  성공 
{% endapi-method-response-example-description %}

```
{"message": "Successful"}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
 로그아웃 실패  
{% endapi-method-response-example-description %}

```
{"message": "Failed"}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

