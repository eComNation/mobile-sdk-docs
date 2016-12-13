## 7. Product Detail

### Files /Classes

1. BaseDetailController
2. ProductDetailController


### Description

The product detail screen displays product's information like product images, name, price, different descriptions, and variants along with lists of similar/related/recently viewed products. It also provides *Add to cart* or *Buy Now* operation to the customer.
To get all the product data make a GET request to **PRODUCT DETAILS URL**

>PRODUCT DETAILS URL

```API
https://abcd.my39shop.com/api/v1/store/products/{product_id}
```

This API returns all the details of the product including a list of related products which is then used directly to display the related products list.


To display similar products we need to fetch the similar products using a separate API call with a GET request to **SIMILAR PRODUCTS URL**

>SIMILAR PRODUCTS URL

```API
https://abcd.my39shop.com/api/v1/store/products/{product_id}/similar_products
```


To display recently viewed products we use the normal product listing API with which we can get the products by passing a comma separated string of all the recent product ids. This ids string, containing ids of 5 products at the most, is stored using shared preference.
Fetch the recent products by making a GET request to **RECENT PRODUCTS URL**

>RECENT PRODUCTS URL

```API
https://abcd.my39shop.com/api/v1/store/products?page=1&per_page=5&facets=false&ids={ids_string}
```


The product detail screen has an *add to favorite* option which requires the customer to login as the API needs customer's access token. If customer is not logged in, on selecting this option customer is taken to the login screen.

To add product as favorite make a POST request to **ADD TO FAVORITE URL**

>ADD TO FAVOURITE URL

```API
https://abcd.my39shop.com/api/v1/store/cart/{cart_token}/add_items?items[][id]={id_value}&items[][quantity]={quantity_value}
```

For Jewelry store app, additional product data from jewelry server is fetched using a GET request **JEWELRY DATA URL**

>JEWELRY DATA URL

```API
https://jewelcommerce.my39shop.com/api/v1/store/products/{product_id}?store_id={store_id_value}
```

Another API call is required to fetch product price data with a GET request to **PRODUCT PRICE DATA**

>PRODUCT PRICE DATA

```API
https://jewelcommerce.my39shop.com/api/v1/store/products/{product_id}/price?store_id={store_id_value}
```

To create a cart or to add an item to cart make a POST request to **ADD TO CART URL**

>ADD TO CART

```API
https://jewelcommerce.my39shop.com/api/v1/store/cart/items?store_id={store_id_value}&product_id={id_value}&quantity={quantity_value}&metal_option_id={metal_option_value}&metal_size_id={metal_size_value}&gem_options[{option_id_value}]={option_value}
```

If cart exists, add an extra parameter *cart_token* to the above URL, absence of it means the method will create a new cart. 


For a market place app, additional data regarding all the vendors for the selected product is fetched using a GET request to **MARKET PLACE URL**


>MARKET PLACE URL

```API
https://marketplace.my39shop.com/api/v1/store/products/{product_id}?store_id={store_id_value}
```

To create a cart or add item to cart for market place app use a POST request with following URL **ADD TO CART WITH MARKET PLACE**

>ADD TO CART WITH MARKET PLACE

```API
https://marketplace.my39shop.com/api/v1/store/cart/items?store_id={store_id_value}&product_id={id_value}&quantity={quantity_value}&metal_option_id={metal_option_value}&metal_size_id={metal_size_value}&gem_options[{option_id_value}]={option_value}
```

If cart exists, add an extra parameter *cart_token* to the above URL, absence of it means the method will create a new cart.

The product detail screen differs for different stores, the way in which data is represented and displayed differs from store to store. We have multiple classes for product detail implementations and the respective detail screen is opened using a switch case statement over a unique scheme value from config file. For example if the scheme is *ABCD* it will open the product detail screen designed for ABCD store, if there is one, else it will open ProductDetailController by defaullt.

All the basic functionalities like get product data, share functionality, add to favorite are implemented in BaseDetailController class. This class is a super class to all product detail activity classes hence all the common functionalities are indirectly present in all sub classes by virtue of inheritance. 
