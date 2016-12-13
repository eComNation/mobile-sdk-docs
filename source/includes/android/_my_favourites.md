## 20. My Favourites

###Files/Classes

1. MyFavouritesActivity

###Description

All the products which are marked as favorites are displayed in a list view in MyFavouritesActivity class. Customer will be taken to product details page once a product is selected, also customer can remove a product which is added in favorite list.
All products are fetched using GET request to **GET FAVOURITE PRODUCTS URL**.

>GET FAVOURITE PRODUCTS URL:

```API
https://abcd.my39shop.com/api/v1/store/customer/favorite_products?access_token={token_value}
```

A favorite product is removed using DELETE request to **DELETE FAVOURITE PRODUCT URL**.

> DELETE FAVOURITE PRODUCT URL

```API
https://abcd.my39shop.com/api/v1/store/customer/favorite_products/{product_id}?access_token={token_value}
```