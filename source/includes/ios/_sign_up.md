## 11. Sign Up

###Files/Classes

1. SignUpController

###Description

Customer sign up needs details like First name, Last name, Username(Email), Phone, Password(twice for confirmation) and Yes or No for marketing mail subscription. Other than Phone all the fields are mandatory. All this data is used to register the customer by making a POST request to the **SIGN UP URL**.

>SIGN UP URL:

```API
https://abcd.my39shop.com/api/v1/store/customer/accounts/sign_up?first_name={firstname_value}&last_name={lastname_value}&login={email_value}&phone={phone_value}&password={password_value}&password_confirmation={password_value}&marketing_mails={0 or 1}
```

This will send an activation link to the registered email address and on clicking it on the device where the app is installed the app is launched as a listener set up to receive the click event. The listener also captures a link containing the registered email id and the activation token required to activate customer’s account.
The account is then activated using a PUT request to **ACTIVATION URL**.

>ACTIVATION URL:

```API
"https://abcd.my39shop.com/api/v1/store/customer/accounts/activate?activation_token={token_value}&login={email_value}
```