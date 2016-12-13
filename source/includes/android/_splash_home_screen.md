## 3. Splash & Home Screen

### Files/Classes:

1. MainActivity
2. HomeMainFragment
3. HomeFragment
4. FeaturedProductsFragment
5. WebHomeFragment


### Description

The splash screen is used to fetch all the data required for app to work normally. The data that is fetched in the background includes


*Categories:* The categories will appear in the navigation menu, each category can have products or further subcategories under it. These categories are fetched by making a GET request to the **CATEGORY URL**.

> CATEGORY URL

```API
https://abcd.my39shop.com/api/v1/store/categories
```


*Banners:* All the banners that are to be displayed in the home screen are fetched by making a GET request with the following **BANNER URL** 

> BANNER URL

```API
https://abcd.my39shop.com/api/v1/store/home_page/banners
```


*Featured Products:*  For fetching featured products make a GET request to **FEATURED PRODUCTS URL**

> FEATURED PRODUCTS URL

```API
https://abcd.my39shop.com/api/v1/store/products/featured
```


*Supported pin codes:* There is no fixed format for the pin code file URL, it varies from store to store


*Discount Coupons:* For fetching all the active discount coupons, make a GET request to **DISCOUNT COUPONS URL**

> DISCOUNT COUPOUNS URL

```API
https://abcd.my39shop.com/api/v1/store/discount_coupons
```


*Countries:* All the countries that are listed when customer adds an address for billing/delivery. Make a GET request with **COUNTRIES URL**

> COUNTRIES URL

```API
https://abcd.my39shop.com /api/v1/countries
```


*Filter Attributes:* The different criteria used for filtering products are fetched by making a GET request to **FILTER ATTRIBUTES URL**

> FILTER ATTRIBUTES URL

```API
https://abcd.my39shop.com/api/v1/store/filter_attributes
```


**The home screen is of two types:**

**Native Home**, where all the data like banners and featured products are displayed natively. The HomeMainFragment is used to create tab implementation where we have two tabs namely, Home and Featured Collection. 

The Home tab displays all the banners related to the store. A banner can be of two types, list banner which is displayed in an automated slideshow and other banners which are displayed one below the other. A banner can have a category id associated with it, on click of such a banner the app takes the customer to the product listing page for that category.
The page footer contains links to different social media page links for the store. This is done in the HomeFragment class.
 
The Featured Collection tab displays a grid view collection of all the featured products. On clicking any of the products the app takes the customer to the product detail screen for the selected product. This is done in the FeaturedProductsFragment class.

If a store does not have any featured products the HomeMainFragment class is bypassed and only the HomeFragment class is used in its place, thus eliminating the tab implementation and hence the featured collection tab.
	
**Web home** implementation uses a web view to display a web page designed specifically for a mobile app, this is achieved in the WebHomeFragment. The URL used for displaying the web home is **WEB HOME URL**

>WEB HOME URL

```API
https://abcd.my39shop.com/pages/mobile_home
```

This web home page can have banners related to categories and/or products as well as featured product collection. These items have their hyperlinks set up in such a way that a category banner will have “category/category_id” at the end of the hyperlink, a product will have *product/product_id* at the end of it. The click events on these items are captured by listening to the reload event of the web view and depending on the content of the link the app takes the customer either to the product listing page of the selected category or the product detail page of the selected product.
