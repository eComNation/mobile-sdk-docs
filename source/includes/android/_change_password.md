## 18. Change Password

###Files/Classes

1. ChangePasswordActivity

###Description

An option to change password will be shown in my account once customer is logged in using valid credentials which he has created during Sign Up process. If the customer logs in with either Facebook or Google then this option will be hidden.

Password is changed in ChangePasswordActivity class using a PUT request to **CHANGE PASSWRD URL**.

>CHANGE PASSWORD URL:

```API
https://abcd.my39shop.com/api/v1/store/customer/change_password?current_password={current_password_value}&new_password={new_password_value}&confirm_password={new_password_value}&access_token={token_value}
```