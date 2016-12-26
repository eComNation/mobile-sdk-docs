## 18. My Favourites

###Files/Classes

1. MyFavouritesController

###Description

All the products which are marked as favorites are displayed in a list view in MyFavouritesController class. Customer will be taken to product details page once a product is selected, also customer can remove a product which is added in favorite list.
All products are fetched using GET request to **GET FAVOURITE PRODUCTS URL**.

<aside class="notice">
GET FAVOURITE PRODUCTS URL:<br/>
https://abcd.my39shop.com/api/v1/store/customer/favorite_products?access_token={token_value}
</aside>

>GET FAVOURITE PRODUCTS URL RESPONSE:

```json
{
	"products":[{
		"id":42923,
		"name":"Solid Wood Coffee Table",
		"category":"Table",
		"price":"6000.0",
		"image_url":"http://d27afjhe0vu8x.cloudfront.net/store_5675/products/81417/13s_thumb.jpg"}],
	"pagination_info":{
		"current_page":1,
		"next_page":null,
		"previous_page":null,
		"total_pages":1,
		"total_entries":1
	}
}
```

A favorite product is removed using DELETE request to **DELETE FAVOURITE PRODUCT URL**.

<aside class="notice">
DELETE FAVOURITE PRODUCT URL:<br/>
https://abcd.my39shop.com/api/v1/store/customer/favorite_products/{product_id}?access_token={token_value}
</aside>

> DELETE FAVOURITE PRODUCT URL RESPONSE

```json
{"result":"success"}
```
