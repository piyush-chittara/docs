---
description: Getting Started
icon: brackets-curly
---

# APIs

### Step 1: Register As Client

To initiate the login process and receive an OTP, send a POST request to the authentication endpoint. The OTP will be sent to the email address you provide.

This call triggers the server to send an OTP to the provided email address. Check your email for the OTP code.

{% openapi src="../../../.gitbook/assets/openapi" path="/login/client" method="post" %}
[openapi](../../../.gitbook/assets/openapi)
{% endopenapi %}

### Step 2: Verify Client

Once you receive the OTP, verify it by sending another POST request to the same endpoint. This request should include both your email address and the OTP you received.

{% openapi src="../../../.gitbook/assets/openapi" path="/login/verify" method="post" %}
[openapi](../../../.gitbook/assets/openapi)
{% endopenapi %}

**Response:**

If the OTP is verified successfully, the response will include your API key:

```json
{
  "success": true,
  "API_KEY": "YOUR_API_KEY_HERE"
}
```

Use this API key for all subsequent API calls by including it in the header of your requests.
