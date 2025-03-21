# Verify

Once you receive the OTP, verify it by sending another POST request to the same endpoint. This request should include both your email address and the OTP you received.



{% openapi src="../../../../.gitbook/assets/swagger (3).yml" path="/login/verify" method="post" %}
[swagger (3).yml](<../../../../.gitbook/assets/swagger (3).yml>)
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
