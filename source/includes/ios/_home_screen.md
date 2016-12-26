## 3. Home Screen

### Files/Classes:

1. DashBoardController
2. WebDashBoardViewController


### Description

The splash screen is used to fetch all the data required for app to work normally. The data that is fetched in the background includes


*Categories:* The categories will appear in the navigation menu, each category can have products or further subcategories under it. These categories are fetched by making a GET request to the **CATEGORY URL**.

<aside class="notice">
CATEGORY URL:<br/>
https://abcd.my39shop.com/api/v1/store/categories
</aside>


> CATEGORY URL RESPONSE

```json
{
 "categories":[
   {"id":5461,"name":"Living Room","parent_id":null,"position":null,"image_url":null},
   {"id":5462,"name":"Bed Room","parent_id":null,"position":null,"image_url":null},
   {"id":5463,"name":"Out Door","parent_id":null,"position":null,"image_url":null},
   {"id":5887,"name":"Chair","parent_id":5461,"position":null,"image_url":null},
   {"id":5886,"name":"Sofa","parent_id":5461,"position":null,"image_url":null},
   {"id":5466,"name":"Cusion Cover","parent_id":5462,"position":null,"image_url":null}]
}
```


*Banners:* All the banners that are to be displayed in the home screen are fetched by making a GET request with the following **BANNER URL** 

<aside class="notice">
BANNER URL:<br/>
https://abcd.my39shop.com/api/v1/store/home_page/banners
</aside>

> BANNER URL RESPONSE

```json
{
 "banners":[
 {"id":203,"position":1,"category_id":null,"url":"//d27afjhe0vu8x.cloudfront.net/store_5675/mobile/banners/203/banner01.png","is_list":true,"dimensions":null},
 {"id":204,"position":2,"category_id":null,"url":"//d27afjhe0vu8x.cloudfront.net/store_5675/mobile/banners/204/banner01.png","is_list":true,"dimensions":null}]
}
```


*Featured Products:*  For fetching featured products make a GET request to **FEATURED PRODUCTS URL**

<aside class="notice">
FEATURED URL:<br/>
https://abcd.my39shop.com/api/v1/store/products/featured
</aside>

> FEATURED PRODUCTS URL

```json
{
 "products":[
  {"id":39119,"name":"Computer Table","sku":"FB08","category_id":5888,"price":"2000.0","previous_price":"2200.0","url":"/products/computer-table-2","product_image_url":"//d27afjhe0vu8x.cloudfront.net/store_5675/products/81441/steelodra-office-table_list.jpg","track_quantity":false,"quantity":1,"minimum_stock_level":0,"created_at":"2016-08-16T03:57:31.000Z","images":[],"options":[],"variants":[]},
  {"id":39122,"name":"Office Table","sku":"FB11","category_id":5465,"price":"600.0","previous_price":null,"url":"/products/office-table","product_image_url":"//d27afjhe0vu8x.cloudfront.net/store_5675/products/73510/modular-office-furniture_list.jpg","track_quantity":false,"quantity":1,"minimum_stock_level":0,"created_at":"2016-08-16T04:03:37.000Z","images":[],"options":[],"variants":[]}],
  "pagination_info":{"current_page":1,"next_page":null,"previous_page":null,"total_pages":1,"total_entries":9}
}
```


*Supported pin codes:* There is no fixed format for the pin code file URL, it varies from store to store


*Discount Coupons:* For fetching all the active discount coupons, make a GET request to **DISCOUNT COUPONS URL**

<aside class="notice">
DISCOUNT COUPOUNS URL:<br/>
https://abcd.my39shop.com/api/v1/store/discount_coupons
</aside>

> DISCOUNT COUPOUNS URL

```json
{
 "discount_coupons":[
 {"id":119,"store_id":5504,"code":"disc10","title":"Discount 10% ","percentage":10.0,"flat_rate":null,"expires_on":"2016-03-24","product_category":null,"product_sku":"PURE-LINE-102","created_at":"2016-03-18T15:29:30.000Z","updated_at":"2016-03-21T07:05:24.000Z","purchase_limit":null,"usage_limit":null},
 {"id":120,"store_id":5504,"code":"TestDiscount10","title":"TestDiscount10","percentage":10.0,"flat_rate":null,"expires_on":"2016-06-08","product_category":null,"product_sku":null,"created_at":"2016-03-23T15:50:51.000Z","updated_at":"2016-06-07T08:16:14.000Z","purchase_limit":null,"usage_limit":null}
 ]
}
```


*Countries:* All the countries that are listed when customer adds an address for billing/delivery. Make a GET request with **COUNTRIES URL**

<aside class="notice">
COUNTRIES URL:<br/>
https://abcd.my39shop.com/api/v1/countries
</aside>

> COUNTRIES URL RESPONSE

```json
{
 "countries":[
 {"id":1,"name":"AFGHANISTAN","iso":"AF","iso3":"AFG"},
 {"id":2,"name":"ALBANIA","iso":"AL","iso3":"ALB"}]
}
```


*Filter Attributes:* The different criteria used for filtering products are fetched by making a GET request to **FILTER ATTRIBUTES URL**

<aside class="notice">
FILTER ATTRIBUTES URL:<br/>
https://abcd.my39shop.com/api/v1/store/filter_attributes
</aside>

> FILTER ATTRIBUTES URL RESPONSE

```json
{
 "filter_attributes":[
 {"id":1468,"name":"sample-attribute-color","values":[{"value":"brown","attribute_index":"sample_attribute_color_brown"}]},
 {"id":1469,"name":"sample-attribute-size","values":[{"value":"large","attribute_index":"sample_attribute_size_large"}]}]
}
```


**The home screen is of two types:**

**Native Home**, where all the data like banners and featured products are displayed natively. The DashBoardController is used to create tab implementation where we have two tabs namely, Home and Featured Collection. 

The Home tab displays all the banners related to the store. A banner can be of two types, list banner which is displayed in an automated slideshow and other banners which are displayed one below the other. A banner can have a category id associated with it, on click of such a banner the app takes the customer to the product listing page for that category.
The page footer contains links to different social media page links for the store. This is done in the HomeFragment class.
 
The Featured Collection tab displays a grid view collection of all the featured products. On clicking any of the products the app takes the customer to the product detail screen for the selected product. This is done in the FeaturedProductsFragment class.

If a store does not have any featured products the tab implementation is removed thus hiding the featured collection tab.

**Web home** implementation uses a web view to display a web page designed specifically for a mobile app, this is achieved in the WebDashBoardViewController. The URL used for displaying the web home is **WEB HOME URL**

<aside class="notice">
WEB HOME URL:<br/>
https://abcd.my39shop.com/pages/mobile_home
</aside>

This web home page can have banners related to categories and/or products as well as featured product collection. These items have their hyperlinks set up in such a way that a category banner will have “category/category_id” at the end of the hyperlink, a product will have *product/product_id* at the end of it. The click events on these items are captured by listening to the reload event of the web view and depending on the content of the link the app takes the customer either to the product listing page of the selected category or the product detail page of the selected product.
