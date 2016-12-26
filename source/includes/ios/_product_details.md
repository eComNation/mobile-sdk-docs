## 7. Product Detail

### Files /Classes

1. BaseDetailController
2. ProductDetailController


### Description

The product detail screen displays product's information like product images, name, price, different descriptions, and variants along with lists of similar/related/recently viewed products. It also provides *Add to cart* or *Buy Now* operation to the customer.
To get all the product data make a GET request to **PRODUCT DETAILS URL**

<aside class="notice">
PRODUCT DETAILS URL:<br/>
https://abcd.my39shop.com/api/v1/store/products/{product_id}
</aside>

>PRODUCT DETAILS URL RESPONSE

```json
{
 "product":
 {"id":6843,
  "category_id":2739,
  "name":"Sample Product 1",
  "description":"This is a sample product",
  "track_quantity":true,
  "permalink":"sample_product_1",
  "images":[{"id":28242,"url":"//d27afjhe0vu8x.cloudfront.net/store_5273/products/28242/sample_product_1.jpg"}],
  "default_variant":{"id":16078,"sku":"SAMPRO1","price":"100.0","previous_price":"125.0","quantity":100,"minimum_stock_level":10},
  "detailed_description":null,
  "filter_attributes":[{"name":"sample-attribute-color","values":["brown"]},{"name":"sample-attribute-size","values":["large"]}],
  "related_products":[],
  "custom_attributes":{},
  "options":[{"id":1701,"name":"option"}],
  "variants":[{"id":16079,"sku":"CARTONBROWN11","price":"100.0","weight":"300.0","quantity":20,"minimum_stock_level":5,"option1":"Carton1","option2":null,"option3":null,"position":null,"image_id":null},{"id":16080,"sku":"CARTONBROWN21","price":"100.0","weight":"300.0","quantity":20,"minimum_stock_level":5,"option1":"Carton2","option2":null,"option3":null,"position":null,"image_id":null}]}
 }
```

This API returns all the details of the product including a list of related products which is then used directly to display the related products list.


To display similar products we need to fetch the similar products using a separate API call with a GET request to **SIMILAR PRODUCTS URL**

<aside class="notice">
SIMILAR PRODUCTS URL:<br/>
https://abcd.my39shop.com/api/v1/store/products/{product_id}/similar_products
</aside>

>SIMILAR PRODUCTS URL RESPONSE

```json
{
 "products":[{
  "id":42961,"name":"Hangit Easy deck wooden chair","price":"3999.0","previous_price":"4999.0","image_url":"https://d27afjhe0vu8x.cloudfront.net/store_5675/products/81402/77_list.jpg"},
  {"id":42958,"name":"Out door Chair Furniture Set","price":"7999.0","previous_price":"9999.0","image_url":"https://d27afjhe0vu8x.cloudfront.net/store_5675/products/81398/70_list.jpg"},
  {"id":42962,"name":"Rocking Chair","price":"1499.0","previous_price":"1599.0","image_url":"https://d27afjhe0vu8x.cloudfront.net/store_5675/products/81397/80_list.jpg"},
  {"id":42960,"name":"Cello Oasis Four Seater Centre Table","price":"899.0","previous_price":"999.0","image_url":"https://d27afjhe0vu8x.cloudfront.net/store_5675/products/81400/75_list.jpg"},
  {"id":39121,"name":"3-Seater-Cast-Iron-Backrest","price":"750.0","previous_price":null,"image_url":"https://d27afjhe0vu8x.cloudfront.net/store_5675/products/81437/Garden-Metal-Bench-3-Seater-Cast-Iron-Backrest-_57_list.jpg"}]
}
```


To display recently viewed products we use the normal product listing API with which we can get the products by passing a comma separated string of all the recent product ids. This ids string, containing ids of 5 products at the most, is stored using shared preference.
Fetch the recent products by making a GET request to **RECENT PRODUCTS URL**

<aside class="notice">
RECENT PRODUCTS URL:<br/>
https://abcd.my39shop.com/api/v1/store/products?page=1&per_page=5&facets=false&ids={ids_string}
</aside>

>RECENT PRODUCTS URL RESPONSE

```json
{
 "products":[{"id":6843,"name":"Sample Product 1","sku":"SAMPRO1","category_id":2739,"price":"100.0","previous_price":"125.0","url":"/products/sample_product_1","product_image_url":"//d27afjhe0vu8x.cloudfront.net/store_5273/products/28242/sample_product_1_list.jpg","track_quantity":true,"quantity":100,"minimum_stock_level":10,"created_at":"2015-09-11T07:21:02.000Z","images":[],"options":[],"variants":[]}],
 "pagination_info":{"current_page":1,"next_page":null,"previous_page":null,"total_pages":1,"total_entries":1}
}
```


The product detail screen has an *add to favorite* option which requires the customer to login as the API needs customer's access token. If customer is not logged in, on selecting this option customer is taken to the login screen.

To add product as favorite make a POST request to **ADD TO FAVORITE URL**

>ADD TO FAVOURITE URL

<aside class="notice">
ADD TO FAVOURITE URL:<br/>
https://abcd.my39shop.com/api/v1/store/cart/{cart_token}/add_items?items[][id]={id_value}&items[][quantity]={quantity_value}
</aside>

For Jewelry store app, additional product data from jewelry server is fetched using a GET request **JEWELRY DATA URL**

<aside class="notice">
JEWELRY DATA URL:<br/>
https://jewelcommerce.my39shop.com/api/v1/store/products/{product_id}?store_id={store_id_value}
</aside>

>JEWELRY DATA URL RESPONSE

```json
{
 "product":{
 "id":"57eca231b630335f31759d93",
 "making_type":"Prong",
 "engrave_charge":0.0,
 "discount":0.0,
 "dimensions":{"height":null,"width":null,"length":null,"depth":null},
 "metal_options":[{"id":"57ecb1b2b630335f31759dfc","name":"Yellow Gold 22K","code":"yellow_gold_22k","is_default":true}],
 "metal_sizes":[{"id":"57ecb1c7b630335f31759dfd","name":"Free Size","weight":5.57,"is_default":true}],
 "gem_options":[{"id":"57ecb1e1b630335f31759e01","name":"Other","number_of_gems":1,"values":[{"id":"57ecb1e1b630335f31759e00","name":"small stone","code":"small_stone","type":"gemstone","shape":null,"clarity":null,"color":null,"carat":0.0,"is_default":true}]}]}
}
```

Another API call is required to fetch product price data with a GET request to **PRODUCT PRICE DATA**

<aside class="notice">
PRODUCT PRICE DATA:<br/>
https://jewelcommerce.my39shop.com/api/v1/store/products/{product_id}/price?store_id={store_id_value}
</aside>

>PRODUCT PRICE DATA RESPONSE

```json
{
 "price":{
  "total":20136,
  "engrave_charge":0,
  "making_charge":3075.0,
  "metal":{"id":"57ecb1b2b630335f31759dfc","name":"Yellow Gold 22K","size":"Free Size","per_gm_rate":3063,"weight":5.57,"price":17061},
  "gem_options":[{"id":"57ecb1e1b630335f31759e01","name":"Other","number_of_gems":1,"value":{"id":"57ecb1e1b630335f31759e00","name":"small stone","carat":0.0,"shape":null,"price":0}}]}
}
```

To create a cart or to add an item to cart make a POST request to **ADD TO CART URL**

<aside class="notice">
ADD TO CART:<br/>
https://jewelcommerce.my39shop.com/api/v1/store/cart/items?store_id={store_id_value}&product_id={id_value}&quantity={quantity_value}&metal_option_id={metal_option_value}&metal_size_id={metal_size_value}&gem_options[{option_id_value}]={option_value}
</aside>

If cart exists, add an extra parameter *cart_token* to the above URL, absence of it means the method will create a new cart. 


For a market place app, additional data regarding all the vendors for the selected product is fetched using a GET request to **MARKET PLACE URL**


<aside class="notice">
MARKET PLACE URL:<br/>
https://marketplace.my39shop.com/api/v1/store/products/{product_id}?store_id={store_id_value}
</aside>

>MARKET PLACE URL RESPONSE

```json
{
"attachment_url":null,
"options":[],
"variants":[],
"vendors":[{"id":"57b3108643aed9698f6de20c","name":"KRNT  Ecommerce","price":620.0,"previous_price":null,"shipping_charge":0.0,"quantity":0,"variants":[]}]
}
```

To create a cart or add item to cart for market place app use a POST request with following URL **ADD TO CART WITH MARKET PLACE**

<aside class="notice">
ADD TO CART WITH MARKET PLACE:<br/>
https://marketplace.my39shop.com/api/v1/store/cart/items?store_id={store_id_value}&product_id={id_value}&quantity={quantity_value}&metal_option_id={metal_option_value}&metal_size_id={metal_size_value}&gem_options[{option_id_value}]={option_value}
</aside>

If cart exists, add an extra parameter *cart_token* to the above URL, absence of it means the method will create a new cart.

The product detail screen differs for different stores, the way in which data is represented and displayed differs from store to store. We have multiple classes for product detail implementations and the respective detail screen is opened using a switch case statement over a unique scheme value from config file. For example if the scheme is *ABCD* it will open the product detail screen designed for ABCD store, if there is one, else it will open ProductDetailController by defaullt.

All the basic functionalities like get product data, share functionality, add to favorite are implemented in BaseDetailController class. This class is a super class to all product detail activity classes hence all the common functionalities are indirectly present in all sub classes by virtue of inheritance. 
