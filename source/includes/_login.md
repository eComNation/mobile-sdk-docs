## 12. Login

###Files/Classes

1. LoginActivity

###Description

There are 3 ways for a customer to log in,

* Native login: The customer can log in with the username and password he has registered with the store by signing up. The login API needs customer’s username and password along with two keys that are required for authentication. These keys are called Client Id and Client Secret, they are unique for each store. The login API needs a POST request to **LOGIN URL**.

>LOGIN URL:

```API
https://abcd.my39shop.com/api/v1/store/customer/accounts/sign_in?login={email_value}&password={password_value}&client_id={id_value}&secret={secret_value}
```

* Login with Google: The app is registered with the Google developer console using it’s package name to enable Google Sign In, a Google client id is generated in this process which is used to obtain a token that is further used in the sign in with Google API which uses the **SIGN IN WITH GOOGLE URL**.

>SIGN IN WITH GOOGLE URL:

```API
https://abcd.my39shop.com/api/v1/store/customer/accounts/sign_in_with_google?access_token={token_value}&client_id={id_value}&secret={secret_value}
```

* Login with Facebook: The app is registered with the Facebook developer console using it’s package name to enable Facebook Sign In, a Facebook App Id is generated in this process which is used to obtain a token that is further used in the sign in with Facebook API which uses the **SIGN IN WITH FACEBOOK URL**.

>SIGN IN WITH FACEBOOK URL:

```API
https://abcd.my39shop.com/api/v1/store/customer/accounts/sign_in_with_facebook?access_token={token_value}&client_id={id_value}&secret={secret_value}
```

Upon login with any of the above methods an access token is generated which is used to authenticate and identify the customer. The app maintains a local copy of the customer’s cart which needs to be synchronized with server copy which is done right after login using the access token.

If there is no local cart, using access token customer’s cart is fetched and stored locally. This is done using a GET request to **GET CART URL**.

>GET CART URL:

```API
https://abcd.my39shop.com/api/v1/store/cart?access_token={token_value}
```

If there is a local copy of the cart, it is associated with the customer, to make sure both the carts are in sync, with a GET request to **ASSOCIATE CART URL**.

>ASSOCIATE CART URL:

```API
https://abcd.my39shop.com/api/v1/store/cart/{cart_token}/associate_cart_to_customer?access_token={token_value}
```
