## 5. Product Listing

### Files/Classes

1. ProductListingActivity
2. SearchActivity


### Description

The product listing page has a grid view collection displaying the products of the currently selected category. The products are sorted according to a default sort criteria. Customer can change the way products are displayed either in grid format or list format if display_option is set to true in config file. Customer can sort products using various sorting options available in sort spinner. Customer can also filter out products by applying various filter options available in filter screen. Once filters are applied a button will be displayed to customer to reset all filters. Upon clicking on product customer is taken to product details page. If *show_out_of_stock* flag is marked true in config then out of stock will be displayed on product image for products with no stock. If *show_favourite_listng* is marked true in config then customer will have favorite icon on product image to directly add product to favorite list.
Data is fetched by making a GET request **PRODUCT LISTING URL**

>PRODUCT LISTING URL

```API
https://abcd.my39shop.com/api/v1/store/products?active_catgory={category_id}&sort_criteria={sort_criteria_value}&facets={false}&per_page={per_page_value}&page={page_value}
```

If out of stock is to be displayed then additional parameter variants with a value 1 will be added to the **PRODUCT LISTING URL**.

Immediately after the above request make another request by just changing the value for facets parameter to true. The result of this request will be used for setting up the filters as explained later.


### Search
Customer can search for a product by clicking search icon, SearchActivity will be opened where customer can type the search criteria and products will be displayed which matches the criteria. Previously searched criteria will be saved in recent searches list and customer can search products again by selecting it. Latest search will be shown on top. Maximum of 10 searches will be saved in recent search list and as the new searches are added old ones are removed from the list. To get data for a search query make a get request to **SEARCH URL**

>SEARCH URL

```API
https://abcd.my39shop.com/api/v1/store/products?search_criteria={search_query}&sort_criteria={sort_criteria_value}&facets={false}&per_page={per_page_value}&page={page_value}
```
