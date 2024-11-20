# Verify

Once you receive the OTP, verify it by sending another POST request to the same endpoint. This request should include both your email address and the OTP you received.

{% swagger src="../../../../.gitbook/assets/openapi '3.0.yml" path="/login/verify" method="post" %}
[openapi '3.0.yml](<../../../../.gitbook/assets/openapi '3.0.yml>)
{% endswagger %}

**Response:**

If the OTP is verified successfully, the response will include your API key:

```json
{
  "success": true,
  "API_KEY": "YOUR_API_KEY_HERE"
}
```

Use this API key for all subsequent API calls by including it in the header of your requests.
