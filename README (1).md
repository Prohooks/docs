---
description: >-
  Welcome to the Prohooks Timers API. The Timers API allows you to schedule
  webhooks with custom request headers and params
---

# Timers

{% hint style="info" %}
Base API URL https://api.prohooks.xyz/timers/
{% endhint %}

### API Methods

{% swagger method="put" path="/new" baseUrl="https://api.proohoks.xyz/timers" summary="Create a Timer" %}
{% swagger-description %}
Schedule a new Timer
{% endswagger-description %}

{% swagger-parameter in="header" name="authorization" required="true" type="String" %}
API Token
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" required="true" type="String" %}
Timer name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="url" required="true" type="String" %}
Webhook Request URL
{% endswagger-parameter %}

{% swagger-parameter in="body" name="method" required="true" type="String" %}
Webhook Request method. One of:\
\- `DELETE`

\- `GET`

\- `HEAD`

\- `OPTIONS`

\- `POST`

\- `PUT`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="duration" required="true" type="String" %}
Timer duration
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payload" type="Any" required="false" %}
Webhook Request body
{% endswagger-parameter %}

{% swagger-parameter in="body" name="headers" type="Object" %}
Webhook Request headers
{% endswagger-parameter %}

{% swagger-parameter in="body" name="include_details" type="Boolean" %}
Whether to send the Timer Object under the 

`timer`

 key in the Webhook Request body. Default 

<mark style="color:orange;">

`false`

</mark>
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Timer Created" %}
```javascript
{
    id: "1oA78CDeeF",
    user: "prohooks_admin",
    url: "https://google.com",
    method: "POST",
    payload: {
        "awesome": true,
    },
    headers: {
        "Content-Type":  "application/json"
    },
    duration: 60,
    include_details: true
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Missing or Invalid Fields" %}

{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="Missing API Token" %}

{% endswagger-response %}

{% swagger-response status="402: Payment Required" description="No Requests" %}

{% endswagger-response %}

{% swagger-response status="403: Forbidden" description="Invalid Token" %}

{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Request Failed" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="/:timer_id" baseUrl="https://api.proohoks.xyz/timers" summary="Retrieve a Timer" expanded="false" %}
{% swagger-description %}
Fetch information about a Timer
{% endswagger-description %}

{% swagger-parameter in="header" name="authorization" type="String" required="true" %}
API Token
{% endswagger-parameter %}

{% swagger-parameter in="path" name="timer_id" type="String" required="true" %}
ID of the Timer to fetch
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Timer Retrieved" %}
```javascript
{
    id: "1oA78CDeeF",
    user: "prohooks_admin",
    url: "https://google.com",
    method: "POST",
    payload: {
        "awesome": true,
    },
    headers: {
        "Content-Type":  "application/json"
    },
    duration: 60,
    include_details: true
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Missing or Invalid Fields" %}

{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="Missing API Token" %}

{% endswagger-response %}

{% swagger-response status="403: Forbidden" description="Invalid API Token" %}

{% endswagger-response %}

{% swagger-response status="404: Not Found" description="Unknown or Invalid Timer ID" %}

{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Request Failed" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="/" baseUrl="https://api.proohoks.xyz/timers" summary="List all Timers" %}
{% swagger-description %}
List all the current user's active Timers
{% endswagger-description %}

{% swagger-parameter in="header" name="authorization" type="String" required="true" %}
API Token
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Timers fetched" %}
```javascript
[
    {
        id: "1oA78CDeeF",
        user: "prohooks_admin",
        url: "https://google.com",
        method: "POST",
        payload: {
            "awesome": true,
        },
        headers: {
            "Content-Type":  "application/json"
        },
        duration: 60,
        include_details: true
    }
]
```
{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="Missing API Token" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="403: Forbidden" description="Invalid API Token" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Request Failed" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="delete" path="/:timer_id" baseUrl="https://api.proohoks.xyz/timers" summary="Delete a Timer" %}
{% swagger-description %}
Cancel a timer
{% endswagger-description %}

{% swagger-parameter in="header" name="authorization" required="true" %}
API token
{% endswagger-parameter %}

{% swagger-parameter in="path" required="true" name="timer_id" %}
ID of the Timer to fetch
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Timer Deleted" %}
```javascript
{
    id: "1oA78CDeeF",
    user: "prohooks_admin",
    url: "https://google.com",
    method: "POST",
    payload: {
        "awesome": true,
    },
    headers: {
        "Content-Type":  "application/json"
    },
    duration: 60,
    include_details: true
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Missing or Invalid Fields" %}

{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="Missing API Token" %}

{% endswagger-response %}

{% swagger-response status="403: Forbidden" description="Invalid API Token" %}

{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Request Failed" %}

{% endswagger-response %}
{% endswagger %}
