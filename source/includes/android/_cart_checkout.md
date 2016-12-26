## 10. Cart & Checkout

###Files/Classes

1. CartCheckoutActivity
2. CartFragment
3. NewCheckoutFragment

###Description

The cart screen displays the content of customer's cart, including cart items with their details, total amount, discount coupons, gift cards, and reward points applied, if any. This is implemented in CartFragment class.
There are multiple API requests in this screen, these include: 

* *Get cart details*: Each cart has a token using which we can get the updated cart by making a GET request to **GET CART URL**.

<aside class="notice">
GET CART URL:<br/>
https://abcd.my39shop.com/api/v1/store/cart/{cart_token}/get
</aside>

>GET CART URL RESPONSE:

```json
{
 "cart":{
	"discount_coupon_id":null,
	"token":"c93e36cd827a007597a29d4ae6104eca",
	"created_at":"2016-10-26T13:28:33.000Z",
	"updated_at":"2016-12-15T18:44:02.000Z",
	"discounted_cart_amount":5000.0,
	"gift_card_amount":0,
	"reward_points":null,
	"points_per_unit_amount":0,
	"available_reward_points":0,
	"group_not_excluded":false,
	"items":[{
		"id":15086,
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

* *Update cart item quantity*: Cart item quantity can be increased or decreased with a PATCH request to **UPDATE QUANTITY URL**.

<aside class="notice">
UPDATE QUANTITY URL:<br/>
https://abcd.my39shop.com/api/v1/store/cart/{cart_token}/update_quantity?id={id_value}&quantity={quantity_value}
</aside>

>UPDATE QUANTITY URL RESPONSE:

```json
{
	"cart":{
		"discount_coupon_id":null,
		"token":"c93e36cd827a007597a29d4ae6104eca",
		"created_at":"2016-10-26T13:28:33.000Z",
		"updated_at":"2016-12-15T18:44:02.000Z",
		"discounted_cart_amount":10000.0,
		"gift_card_amount":0,
		"reward_points":null,
		"points_per_unit_amount":0,
		"available_reward_points":0,
		"group_not_excluded":false,
		"items":[{
			"id":15086,
			"variant_id":70131,
			"quantity":2,
			"actual_price":"10000.0",
			"discounted_price":"10000.0",
			"sku":"FB20",
			"name":"VAS Collection Home Solid Wood Coffee Table",
			"image_url":"//d27afjhe0vu8x.cloudfront.net/store_5675/products/81409/19s_thumb.jpeg",
			"max_quantity_possible":null,
			"custom_details":null,
			"external_details":null}]
		}
}
```

* *Remove cart item*: Cart item can be removed with a DELETE request to **REMOVE ITEM URL**.

<aside class="notice">
REMOVE ITEM URL:<br/>
https://abcd.my39shop.com/api/v1/store/cart/{cart_token}/delete?items[][id]={id_value}
</aside>

>REMOVE ITEM URL RESPONSE:

```json
{
	"cart":{
		"discount_coupon_id":null,
		"token":"c93e36cd827a007597a29d4ae6104eca",
		"created_at":"2016-10-26T13:28:33.000Z",
		"updated_at":"2016-12-15T18:44:02.000Z",
		"discounted_cart_amount":0.0,
		"gift_card_amount":0,
		"reward_points":null,
		"points_per_unit_amount":0,
		"available_reward_points":0,
		"group_not_excluded":false,
		"items":[]
	}
}
```

* *Apply discount coupon*:  To apply a discount coupon or a gift card make a PATCH request to **APPLY COUPON URL**.

<aside class="notice">
APPLY COUPON URL:<br/>
https://abcd.my39shop.com/api/v1/store/cart/{cart_token}/apply_discount_coupon?discount_coupon_code={coupon_value}
</aside>

>APPLY COUPON URL RESPONSE:

```json
{
	"cart":{
		"discount_coupon_id":190,
		"token":"c93e36cd827a007597a29d4ae6104eca",
		"created_at":"2016-10-26T13:28:33.000Z",
		"updated_at":"2016-12-23T11:54:22.000Z",
		"discounted_cart_amount":4500.0,
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
			"discounted_price":"4500.0",
			"sku":"FB20",
			"name":"VAS Collection Home Solid Wood Coffee Table",
			"image_url":"//d27afjhe0vu8x.cloudfront.net/store_5675/products/81409/19s_thumb.jpeg",
			"max_quantity_possible":null,
			"custom_details":null,
			"external_details":null}]
	}
}
```

* *Remove discount coupon*: To remove a discount coupon make a PATCH request to **REMOVE COUPON URL**.

<aside class="notice">
REMOVE COUPON URL:<br/>
https://abcd.my39shop.com/api/v1/store/cart/{cart_token}/remove_discount_coupon
</aside>

>REMOVE COUPON URL:

```json
{
	"cart":{
		"discount_coupon_id":null,
		"token":"c93e36cd827a007597a29d4ae6104eca",
		"created_at":"2016-10-26T13:28:33.000Z",
		"updated_at":"2016-12-23T11:58:27.000Z",
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

* *Remove gift card*: To remove a gift card make a PATCH request to **REMOVE GIFT CARD URL**.

<aside class="notice">
REMOVE GIFT CARD URL:<br/>
https://abcd.my39shop.com/api/v1/store/cart/{cart_token}/remove_gift_card
</aside>

>REMOVE GIFT CARD URL RESPONSE:

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

* *Apply reward points*: Reward points can be applied with a PATCH request to **APPLY REWARD POINTS URL**.

<aside class="notice">
APPLY REWARD POINTS URL:<br/>
https://abcd.my39shop.com/api/v1/store/cart/{cart_token}/apply_reward_points?reward_points={reward_points_value}
</aside>

* *Remove reward points*: Reward points can be removed with a PATCH request to **REMOVE GIFT CARD URL**.

<aside class="notice">
REMOVE REWARD POINTS URL:<br/>
https://abcd.my39shop.com/api/v1/store/cart/{cart_token}/remove_reward_points
</aside>

All the above calls, except get cart, can have an additional parameter in access_token if the customer is logged in.

The checkout is implemented in a webview using the checkout process of the web store.
When the customer proceeds to checkout, if not logged in, he/she is asked to log in with an option to checkout as guest.

To start checkout, following **CHECKOUT URL** is opened in the webview.

<aside class="notice">
CHECKOUT URL:<br/>
https://abcd.my39shop.com/checkouts/init?cart_id={cart_token_value}&is_mobile={true}
</aside>

If the customer is logged in, append access_token parameter to the above URL. 

The customer then follows the checkout steps as the app takes him/her forward through the webview. We listen to the reload event of the web view and depending on the content of the URL that is loaded the app takes certain actions. If the URL contains the word “confirm” it means that customer has successfully placed the order so we clear the cart and on the next reload take the customer to the home screen.
