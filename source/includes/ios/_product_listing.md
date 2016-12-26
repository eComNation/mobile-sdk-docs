## 5. Product Listing

### Files/Classes

1. ProductListController
2. SearchController


### Description

The product listing page has a grid view collection displaying the products of the currently selected category. The products are sorted according to a default sort criteria. Customer can change the way products are displayed either in grid format or list format if display_option is set to true in config file. Customer can sort products using various sorting options available in sort spinner. Customer can also filter out products by applying various filter options available in filter screen. Once filters are applied a button will be displayed to customer to reset all filters. Upon clicking on product customer is taken to product details page. If *show_out_of_stock* flag is marked true in config then out of stock will be displayed on product image for products with no stock. If *show_favourite_listng* is marked true in config then customer will have favorite icon on product image to directly add product to favorite list.
Data is fetched by making a GET request **PRODUCT LISTING URL**

<aside class="notice">
PRODUCT LISTING URL:<br/>
https://abcd.my39shop.com/api/v1/store/products?active_catgory={category_id}&sort_criteria={sort_criteria_value}&facets={false}&per_page={per_page_value}&page={page_value}
</aside>

>PRODUCT LISTING URL RESPONSE

```json
{
 "products":[{"id":6843,"name":"Sample Product 1","sku":"SAMPRO1","category_id":2739,"price":"100.0","previous_price":"125.0","url":"/products/sample_product_1","product_image_url":"//d27afjhe0vu8x.cloudfront.net/store_5273/products/28242/sample_product_1_list.jpg","track_quantity":true,"quantity":100,"minimum_stock_level":10,"created_at":"2015-09-11T07:21:02.000Z","images":[],"options":[],"variants":[]}],
 "pagination_info":{"current_page":1,"next_page":null,"previous_page":null,"total_pages":1,"total_entries":1}
}
```

If out of stock is to be displayed then additional parameter variants with a value 1 will be added to the **PRODUCT LISTING URL**.

Immediately after the above request make another request by just changing the value for facets parameter to true. The result of this request will be used for setting up the filters as explained later.


### Search
Customer can search for a product by clicking search icon, SearchController will be opened where customer can type the search criteria and products will be displayed which matches the criteria. Previously searched criteria will be saved in recent searches list and customer can search products again by selecting it. Latest search will be shown on top. Maximum of 10 searches will be saved in recent search list and as the new searches are added old ones are removed from the list. To get data for a search query make a get request to **SEARCH URL**

<aside class="notice">
SEARCH URL:<br/>
https://abcd.my39shop.com/api/v1/store/products?search_criteria={search_query}&sort_criteria={sort_criteria_value}&facets={false}&per_page={per_page_value}&page={page_value}
</aside>

>SEARCH URL RESPONSE

```json
{
 "products":[{"id":6843,"name":"Sample Product 1","sku":"SAMPRO1","category_id":2739,"price":"100.0","previous_price":"125.0","url":"/products/sample_product_1","product_image_url":"//d27afjhe0vu8x.cloudfront.net/store_5273/products/28242/sample_product_1_list.jpg","track_quantity":true,"quantity":100,"minimum_stock_level":10,"created_at":"2015-09-11T07:21:02.000Z","images":[],"options":[],"variants":[]}],
 "pagination_info":{"current_page":1,"next_page":null,"previous_page":null,"total_pages":1,"total_entries":1}
}
```

### Filters

The filter attributes fetched at app start up are used in the filters screen, which returns all the attributes with attribute indices as key-value pairs. When product listing is opened the products will either belong to a category or a result of a search query. So when customer opens the filter screen we need to only show those attributes that are relevant to the current collection of products.
For doing this, as explained above, we need to make a call to the same API (first call) that was called for either category listing or a search query with just a single change in the parameters. The parameters “facets” is by default false in the first call and then we have sent it as true in the second call without changing any other parameter. This returns a list of attribute indices that are relevant to the current list of products, using which we can hide the non –relevant attributes.
Once the customer selects the filters make a GET request using the same API with an extra parameter called filter_attributes and its value should be a comma separated string of all the selected filter attribute indices.

