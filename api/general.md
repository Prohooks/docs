---
description: Welcome to the Prohooks API Docs! Currently, we only have the Timers API
---

# General

## Getting Started

To use the Prohooks APIs, you will need a Prohooks Account & API Token.

To create an account, simply head to [prohooks.xyz/login](https://prohooks.xyz/login) and fill your details.

<figure><img src="../.gitbook/assets/Getting Started #1.png" alt=""><figcaption><p>Prohooks Sign Up</p></figcaption></figure>

Now that you've got an account, you will need to get your API Token. This can be found on your _Account_ page, under _<mark style="color:blue;">**Account**</mark>_ in the user dropdown, or right [here](https://prohooks.xyz/account)! Easy.

<figure><img src="../.gitbook/assets/Getting Started #2.png" alt=""><figcaption><p>User Account dropdown menu</p></figcaption></figure>

To copy your API Key, simply locate the box labelled <mark style="color:blue;">**API Key**</mark> and click the _<mark style="color:blue;">**Copy**</mark>_ button

<figure><img src="../.gitbook/assets/Getting Started #3.png" alt=""><figcaption><p>User Account Management Page</p></figcaption></figure>

If ever your API Key gets leaked, you can click the _<mark style="color:blue;">**Regenerate**</mark>_ button and your old API Key will be invalidated.

{% hint style="danger" %}
Regenerating your API Key will cause any requests using it to fail! Make sure you update your code with the new Key
{% endhint %}

## Sending Requests

When sending a request to any Prohooks API, you will need to provide your API Token in the `authorization` header. Not doing so will return a <mark style="color:red;">`401`</mark> and providing an invalid token will return a <mark style="color:red;">`403`</mark>.

Creating a new Timer will use 1 request. If you attempt to create a timer and don't have any requests, the API will return a <mark style="color:red;">`402`</mark>. You can purchase more requests [here](https://prohooks.xyz/pricing). You can also view your current request count on your [_Account_ page](https://prohooks.xyz/account).&#x20;

<figure><img src="../.gitbook/assets/Sending Requests #1.png" alt=""><figcaption><p>Request count on the Account page</p></figcaption></figure>

