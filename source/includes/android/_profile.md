## 19. Profile

###Files/Classes

1. ProfileActivity

###Description

Customer’s basic profile info like his/her name, mobile number, email address is displayed in this screen. Customer can also update his profile info, except the email address. This is implemented in ProfileActivity class.
Profile info is fetched using GET request to **GET PROFILE INFO URL**.

<aside class="notice">
GET PROFILE INFO URL:<br/>
https://abcd.my39shop.com/api/v1/store/customer/profile?access_token={token_value}
</aside>

>GET PROFILE INFO URL RESPONSE:

```json
{
	"customer":{
		"first_name":"chetan",
		"last_name":"kumar",
		"email":"che@gmail.com",
		"phone":"9696969696"
	}
}
```

Profile data is updated using a PUT request to **UPDATE PROFILE URL**.

<aside class="notice">
UPDATE PROFILE URL:<br/>
https://abcd.my39shop.com/api/v1/store/customer/update_profile?first_name={firstname_value}&last_name={lastname_value}&phone={phone_value}&access_token={token_value}
</aside>

>UPDATE PROFILE URL RESPONSE:

```json
{
	"customer":{
		"first_name":"chetan",
		"last_name":"kumar",
		"email":"che@gmail.com",
		"phone":"9696969696"
	}
}
```
