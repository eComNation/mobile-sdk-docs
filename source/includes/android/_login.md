## 12. Login

###Files/Classes

1. LoginActivity

###Description

There are 3 ways for a customer to log in,

* Native login: The customer can log in with the username and password he has registered with the store by signing up. The login API needs customer’s username and password along with two keys that are required for authentication. These keys are called Client Id and Client Secret, they are unique for each store. The login API needs a POST request to **LOGIN URL**.

<aside class="notice">
LOGIN URL:<br/>
https://abcd.my39shop.com/api/v1/store/customer/accounts/sign_in?login={email_value}&password={password_value}&client_id={id_value}&secret={secret_value}
</aside>

>LOGIN URL RESPONSE:

```json
{
	"access_token":"9e7c792d15324cc8d806d3e5aa3e76ceae",
	"refresh_token":"f0fa0d3df22b8987e421462adae8325b3e",
	"expires_in":604800,
	"created_at":"2016-12-23T11:50:58.000Z"
}
```

* Login with Google: The app is registered with the Google developer console using it’s package name to enable Google Sign In, a Google client id is generated in this process which is used to obtain a token that is further used in the sign in with Google API which uses the **SIGN IN WITH GOOGLE URL**.

<aside class="notice">
SIGN IN WITH GOOGLE URL:<br/>
https://abcd.my39shop.com/api/v1/store/customer/accounts/sign_in_with_google?access_token={token_value}&client_id={id_value}&secret={secret_value}
</aside>

* Login with Facebook: The app is registered with the Facebook developer console using it’s package name to enable Facebook Sign In, a Facebook App Id is generated in this process which is used to obtain a token that is further used in the sign in with Facebook API which uses the **SIGN IN WITH FACEBOOK URL**.

<aside class="notice">
SIGN IN WITH FACEBOOK URL:<br/>
https://abcd.my39shop.com/api/v1/store/customer/accounts/sign_in_with_facebook?access_token={token_value}&client_id={id_value}&secret={secret_value}
</aside>

Upon login with any of the above methods an access token is generated which is used to authenticate and identify the customer. The app maintains a local copy of the customer’s cart which needs to be synchronized with server copy which is done right after login using the access token.

If there is no local cart, using access token customer’s cart is fetched and stored locally. This is done using a GET request to **GET CART URL**.

<aside class="notice">
GET CART URL:<br/>
https://abcd.my39shop.com/api/v1/store/cart?access_token={token_value}
</aside>

>GET CART URL RESPONSE:

```json
{
	"cart":{
		"discount_coupon_id":null,
		"token":"c93e36cd827a007597a29d4ae6104eca",
		"created_at":"2016-10-26T13:28:33.000Z",
		"updated_at":"2016-12-26T05:53:04.000Z",
		"discounted_cart_amount":5000.0,
		"gift_card_amount":0,
		"reward_points":null,
		"points_per_unit_amount":0,
		"available_reward_points":0,
		"group_not_excluded":false,
		"items":[{
			"id":15154,
			"variant_id":70131,
			"quantity":1,
			"actual_price":"5000.0",
			"discounted_price":"5000.0",
			"sku":"FB20",
			"name":"VAS Collection Home Solid Wood Coffee Table",
			"image_url":"//d27afjhe0vu8x.cloudfront.net/store_5675/products/81409/19s_thumb.jpeg",
			"max_quantity_possible":null,
			"custom_details":null,
			"external_details":null}]
	}
}
```

If there is a local copy of the cart, it is associated with the customer, to make sure both the carts are in sync, with a GET request to **ASSOCIATE CART URL**.

<aside class="notice">
ASSOCIATE CART URL:<br/>
https://abcd.my39shop.com/api/v1/store/cart/{cart_token}/associate_cart_to_customer?access_token={token_value}
</aside>

>ASSOCIATE CART URL: RESPONSE:

```json
{
	"cart":{
		"discount_coupon_id":null,
		"token":"c93e36cd827a007597a29d4ae6104eca",
		"created_at":"2016-10-26T13:28:33.000Z",
		"updated_at":"2016-12-26T05:53:04.000Z",
		"discounted_cart_amount":5000.0,
		"gift_card_amount":0,
		"reward_points":null,
		"points_per_unit_amount":0,
		"available_reward_points":0,
		"group_not_excluded":false,
		"items":[{
			"id":15154,
			"variant_id":70131,
			"quantity":1,
			"actual_price":"5000.0",
			"discounted_price":"5000.0",
			"sku":"FB20",
			"name":"VAS Collection Home Solid Wood Coffee Table",
			"image_url":"//d27afjhe0vu8x.cloudfront.net/store_5675/products/81409/19s_thumb.jpeg",
			"max_quantity_possible":null,
			"custom_details":null,
			"external_details":null}]
	}
}
```