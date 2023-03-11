---
description: Welcome to the Prohooks Timers API
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
Required fields were not provided or invalid. Please see above for more information
{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="Missing API Token" %}
No API Token was provided in the 

`authorization`

 header
{% endswagger-response %}

{% swagger-response status="402: Payment Required" description="No Requests" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="403: Forbidden" description="Invalid Token" %}
The API Token in the 

`authorization`

 header was not valid
{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Request Failed" %}
An unkown error occurred. Please report the response Error Object to a staff member so we can fix it!
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
Required fields were not provided or invalid. Please see above for more information
{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="Missing API Token" %}
No API Token was provided in the 

`authorization`

 header
{% endswagger-response %}

{% swagger-response status="403: Forbidden" description="Invalid Token" %}
The API Token in the 

`authorization`

 header was not valid
{% endswagger-response %}

{% swagger-response status="404: Not Found" description="Unknown or Invalid Timer ID" %}
The provided Timer ID was not valid or does not belong to the current user
{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Request Failed" %}
An unkown error occurred. Please report the response Error Object to a staff member so we can fix it!
{% endswagger-response %}
{% endswagger %}

{% swagger method="delete" path="/" baseUrl="https://api.proohoks.xyz/timers" summary="Delete a Timer" %}
{% swagger-description %}
Cancel a timer
{% endswagger-description %}

{% swagger-parameter in="header" name="authorization" required="true" %}
API token
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript

{

    error: false,

    message: "cancelled"

}

```
{% endswagger-response %}
{% endswagger %}
