## 12. Forgot Password

###Files/Classes

1. ForgotPasswordController

###Description

The forgot password screen lets the customer request a change of password by first giving an option to reset the password using his/her registered email address which sends a password reset link and then letting the customer set a new password using the password by launching the app when customer clicks on the link with help of a listener. The listener also captures a link containing a recovery token for setting a new password.
To send a reset link make a GET request to **RESET PASSWORD URL**.

>RESET PASSWORD URL:

```API
https://abcd.my39shop.com/api/v1/store/customer/accounts/forgot_password?login={email_value}
```

To set a new password, make a PUT request to **NEW PASSWORD URL**.

> NEW PASSWORD URL:

```API
https://abcd.my39shop.com/api/v1/store/customer/accounts/set_password?recovery_token={token_value}&password={password_value}&password_confirmation={password_value}
```