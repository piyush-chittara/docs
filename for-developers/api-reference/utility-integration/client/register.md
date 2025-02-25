# Register

To initiate the login process and receive an OTP, send a POST request to the authentication endpoint. The OTP will be sent to the email address you provide.

This call triggers the server to send an OTP to the provided email address. Check your email for the OTP code.

{% openapi src="../../../../.gitbook/assets/openapi" path="/login/client" method="post" %}
[openapi](../../../../.gitbook/assets/openapi)
{% endopenapi %}
