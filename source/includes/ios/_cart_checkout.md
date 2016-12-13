## 8. Cart & Checkout

###Files/Classes

1. CartController

###Description

The cart screen displays the content of customer's cart, including cart items with their details, total amount, discount coupons, gift cards, and reward points applied, if any. This is implemented in CartFragment class.
There are multiple API requests in this screen, these include: 

1. *Get cart details*: Each cart has a token using which we can get the updated cart by making a GET request to **GET CART URL**.

>GET CART URL:

```API
https://abcd.my39shop.com/api/v1/store/cart/{cart_token}/get
```

2. *Update cart item quantity*: Cart item quantity can be increased or decreased with a PATCH request to **UPDATE QUANTITY URL**.

>UPDATE QUANTITY URL

```API 
https://abcd.my39shop.com/api/v1/store/cart/{cart_token}/update_quantity?id={id_value}&quantity={quantity_value}
```

3. *Remove cart item*: Cart item can be removed with a DELETE request to **REMOVE ITEM URL**.

>REMOVE ITEM URL:

```API
https://abcd.my39shop.com/api/v1/store/cart/{cart_token}/delete?items[][id]={id_value}
```

4. *Apply discount coupon*:  To apply a discount coupon or a gift card make a PATCH request to **APPLY COUPON URL**.

>APPLY COUPON URL:

```API
https://abcd.my39shop.com/api/v1/store/cart/{cart_token}/apply_discount_coupon?discount_coupon_code={coupon_value}
```

5. *Remove discount coupon*: To remove a discount coupon make a PATCH request to **REMOVE COUPON URL**.

>REMOVE COUPON URL:

```API
https://abcd.my39shop.com/api/v1/store/cart/{cart_token}/remove_discount_coupon
```

6. *Remove gift card*: To remove a gift card make a PATCH request to **REMOVE GIFT CARD URL**.

>REMOVE GIFT CARD URL:

```API
https://abcd.my39shop.com/api/v1/store/cart/{cart_token}/remove_gift_card
```

7. *Apply reward points*: Reward points can be applied with a PATCH request to **APPLY REWARD POINTS URL**.

>APPLY REWARD POINTS URL:

```API
https://abcd.my39shop.com/api/v1/store/cart/{cart_token}/apply_reward_points?reward_points={reward_points_value}
```

8. *Remove reward points*: Reward points can be removed with a PATCH request to **REMOVE GIFT CARD URL**.

>REMOVE GIFT CARD URL:

```API
https://abcd.my39shop.com/api/v1/store/cart/{cart_token}/remove_reward_points
```

All the above calls, except get cart, can have an additional parameter in access_token if the customer is logged in.

The checkout is implemented in a webview using the checkout process of the web store.
When the customer proceeds to checkout, if not logged in, he/she is asked to log in with an option to checkout as guest.

To start checkout, following **CHECKOUT URL** is opened in the webview.

>CHECKOUT URL:

```API
https://abcd.my39shop.com/checkouts/init?cart_id={cart_token_value}&is_mobile={true}
```

If the customer is logged in, append access_token parameter to the above URL. 

The customer then follows the checkout steps as the app takes him/her forward through the webview. We listen to the reload event of the web view and depending on the content of the URL that is loaded the app takes certain actions. If the URL contains the word “confirm” it means that customer has successfully placed the order so we clear the cart and on the next reload take the customer to the home screen.