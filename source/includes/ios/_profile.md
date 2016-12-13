## 17. Profile

###Files/Classes

1. ProfileController 

###Description

Customer’s basic profile info like his/her name, mobile number, email address is displayed in this screen. Customer can also update his profile info, except the email address. This is implemented in ProfileController class.
Profile info is fetched using GET request to **GET PROFILE INFO URL**.

>GET PROFILE INFO URL:

```API
https://abcd.my39shop.com/api/v1/store/customer/profile?access_token={token_value}
```

Profile data is updated using a PUT request to **UPDATE PROFILE URL**.

>UPDATE PROFILE URL:

```API
https://abcd.my39shop.com/api/v1/store/customer/update_profile?first_name={firstname_value}&last_name={lastname_value}&phone={phone_value}&access_token={token_value}
```
