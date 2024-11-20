# Register

To initiate the login process and receive an OTP, send a POST request to the authentication endpoint. The OTP will be sent to the email address you provide.

This call triggers the server to send an OTP to the provided email address. Check your email for the OTP code.

{% swagger src="../../../../.gitbook/assets/openapi '3.0.yml" path="/login/client" method="post" %}
[openapi '3.0.yml](<../../../../.gitbook/assets/openapi '3.0.yml>)
{% endswagger %}

