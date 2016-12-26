## 14. My Orders

###Files/Classes

1. MyOrdersController 
2. OrderDetailsController

###Description

Customer orders will be fetched and displayed using in a list view. Once customer will click on a particular order he/she will be taken to order details screen. This is implemented in MyOrdersController class.
Orders are fetched using the GET request to **GET ORDERS URL**.

<aside class="notice">
GET ORDERS URL:<br/>
https://abcd.my39shop.com/api/v1/store/customer/orders?access_token={token_value}
</aside>

>GET ORDERS URL RESPONSE:

```json
{
	"orders":[{
		"id":10571,
		"number":"100003",
		"is_viewed":true,
		"created_at":"2016-12-15T18:48:29.000Z",
		"updated_at":"2016-12-16T05:25:09.000Z",
		"order_status":{"id":1,"name":"Pending"},
		"grand_total":"2000.0",
		"total_items":1,
		"order_process_status_id":4,
		"billing_address":{
			"id":30885,
			"first_name":"chetan",
			"last_name":"kumar",
			"address1":"Tivrem",
			"address2":"Marcela",
			"city":"Ponda",
			"state_id":62,
			"state_name":"Goa",
			"country_id":99,
			"country_name":"India",
			"zipcode":"403107",
			"phone":"9696969696"}
		}],
	"pagination_info":{
		"current_page":1,
		"next_page":null,
		"previous_page":null,
		"total_pages":1,
		"total_entries":1}
}
```

Order Details are fetched using a GET request to **GET ORDER DETAIL URL**.

<aside class="notice">
GET ORDER DETAIL URL:<br/>
https://abcd.my39shop.com/api/v1/store/customer/orders/{order_id}?access_token={token_value}
</aside>

>GET ORDER DETAIL URL RESPONSE:

```json
{
	"order":{
		"id":10571,
		"store_id":5675,
		"number":"100003",
		"customer_email":"chetan.teli09@gmail.com",
		"order_status":{"id":1,"name":"Pending"},
		"order_tax_detail":{},
		"shipping_detail":{"delivery_type":"Standard delivery"},
		"payment_detail":{"payment_mode":"Cash on delivery","custom_payment_detail":null},
		"is_viewed":true,
		"payment_processing_charge":null,
		"is_tax_calculated":true,
		"discount":null,
		"discounted_amount":"2000.0",
		"shipping_charge":"0.0",
		"tax_amount":"0.0",
		"sub_total":"2000.0",
		"grand_total":"2000.0",
		"actual_amount":"2000.0",
		"created_at":"2016-12-15T18:48:29.000Z",
		"updated_at":"2016-12-16T05:25:09.000Z",
		"order_process_status_id":4,
		"total_items":1,
		"order_process_logs":[],
		"order_line_items":[{
			"id":13660,
			"order_id":10571,
			"variant_id":65004,
			"quantity":1,
			"discounted_price":"2000.0",
			"name":"Computer Table",
			"sku":"FB08",
			"actual_price":"2000.0",
			"custom_details":null,
			"status_id":"1",
			"product_id":39119,
			"external_details":null,
			"image_url":"http://d27afjhe0vu8x.cloudfront.net/store_5675/products/81441/steelodra-office-table_thumb.jpg"}],
		"shipping_address":{
			"id":30886,
			"first_name":"chetan",
			"last_name":"kumar",
			"address1":"Tivrem",
			"address2":"Marcela",
			"city":"Ponda",
			"state_id":62,
			"state_name":"Goa",
			"country_id":99,
			"country_name":"India",
			"zipcode":"403107",
			"phone":"9696969696"},
		"billing_address":{
			"id":30885,
			"first_name":"chetan",
			"last_name":"kumar",
			"address1":"Tivrem",
			"address2":"Marcela",
			"city":"Ponda",
			"state_id":62,
			"state_name":"Goa",
			"country_id":99,
			"country_name":"India",
			"zipcode":"403107",
			"phone":"9696969696"},
		"order_transaction":{
			"id":5787,
			"order_id":10571,
			"transaction_key":null,
			"created_at":"2016-12-15T18:48:29.000Z",
			"updated_at":"2016-12-15T18:48:29.000Z",
			"payment_method":"custom_payment",
			"payment_processing_charge_rules":{
				"processing_charge_type":null,
				"processing_charge":null,
				"processing_charge_rule":null,
				"processing_charge_applicable_to":null},
			"discount_coupon_rules":{},
			"logs":null
		}
	}
}
```