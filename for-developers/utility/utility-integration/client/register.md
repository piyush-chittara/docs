# Register

To initiate the login process and receive an OTP, send a POST request to the authentication endpoint. The OTP will be sent to the email address you provide.

This call triggers the server to send an OTP to the provided email address. Check your email for the OTP code.



{% openapi src="../../../../.gitbook/assets/swagger (3).yml" path="/login/client" method="post" %}
[swagger (3).yml](<../../../../.gitbook/assets/swagger (3).yml>)
{% endopenapi %}
