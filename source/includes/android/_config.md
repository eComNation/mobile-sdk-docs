## 2. Config File

Config file is an xml file containing different store related values in boolean, color, dimensions, string, string arrays.

### Boolean values

1. *has_display_option* :
If set to true, there will be a button displayed in listing page with which customer can change the way products are displayed (either list view or grid view) else button will be hidden.
2. *show_favourite_listing* :
If set to true, there will be a favorite icon displayed on every product in product listing page with which customer can directly add a product to his/her favorite list.
3. *show_small_description* :
If set to true, a short product description will be displayed below product price in product details page.
4. *show_description* :
Product description will be displayed in the descriptions tabs in product details page if set true.
5. *show_attributes* :
Product filter attribute details as key value pairs will be shown in product descriptions tabs in product details page if set true.
6. *registration_mandatory* :
If true, log in page will be visible before proceeding to checkout and customer will have to Sign in with valid credentials or login with Facebook or google, if set to false checkout as guest link will be visible in login page and customer can proceed to checkout as guest without logging in. 
7. *show_login_startup* :
After splash screen Login page will be displayed to customer if value is set to true when app is opened else home page will be displayed directly after splash screen.
8. *show_web_home* :
Html home page will be displayed instead of native home screen if value is set to true else native home screen will be displayed.
9. *show_loader_icon* :
In product listing page store logo icon will be displayed instead of progress bar until product image is loading.

### Dimension values

1. *list_item_height* :
Layout height to display individual product in listing page is set using this value, it is adjusted depending on the product image dimensions. 250dp is the ideal value.
2. *image_height* :
It is used to display product image in product details page and adjusted depending on the product image dimensions. 360dp is the ideal value.
3. *small_item_height* :
It is used to set height of individual product layout which is used to display similar or recently or related product in product details page. 200dp ideal value.
4. *navigation_drawer_width* :
Drawer width in home page is set using this value. Value ranges from 180dp to 320dp, set depending on text length displayed in drawer.

### Color values

1. *SplashColor* :
Sets background color of splash screen.
2. DrawerItemBack* :
Sets background color of app drawer items in home page.
3. *PrimaryColor* :
App header color is set using this value throughout the application.
4. *FadedPrimaryColor* :
If tabs are present in home screen then the tab header text color which is not selected is set using this value. Generally this color is set either darker or lighter shade of primary color.
5. *PercentageColor* :
This color is used to display percentage off on product price in product details page.
6. *SecondaryColor* :
This color is used as background color of all button, number of cart items displayed in header and also favorite icon when a particular product is added to favorite list. Also this color is used as text color which acts as a clickable link.
7. *FadedSecondaryColor* :
Generally this color is darker or lighter shade of secondary color, used as background of buttons in clicked mode.
8. *MenuTextColor* :
Text which is displayed on app drawer is set using this color value.
9. *MenuBackground* :
Background color behind store logo in app drawer is set using this color value.
10. *FooterColor* :
Footer background color in home page is set using this color value.
11. *CopyrightText* :
Copyright text shown in footer uses this color value.

###String values

1. *store_id* :
It is the store id associated with each store.
2. *facebook_app_id* :
Facebook id which we get when app is created on Facebook developers page with which we can use Log In with Facebook feature.  If kept blank then Facebook button will not be visible in Log In page.
3. *server_client_id* :
Google id which we get when app is created in Google developers page with which we can use Log In with Google feature.  If kept blank then Google button will not be visible in Log In page.
4. *http* :
Stores **http://** value.
5. *store_url* :
The actual URL of the store which is visible to the end customer.  This is used in android manifest file for push notification feature.
Example:  http://abc.com
6. *product_url* :
Product URL of the store where all products are displayed.  This is used when customer shares a particular product to other customers.
Example:  abc.com/products/
7. *production_base_url* :
Stores URL of the store. This is used for API requests to fetch respective data.
Example: http:// abc.my39shop.com/
8. *app_name* :
Stores name of the app or store name.
9. *scheme* : 
Scheme stores value which is unique to store, with the help of this we can retrieve respective stores product details page. Also used to show any special feature in common pages. Basically scheme value is set as store name or name used in URL 
10. *sign_up_url* :
Stores value which will be used during Sign up feature.
Example: signup.abc.com
11. *forgot_password_url* :
Stores value which will be used during forgot password feature.
Example: forgotpassword.abc.com
12. *pincode_url* :
Stores URL of the file where all pin code values are stored. If kept blank then the pin code checker functionality is disabled product details page.
13. *misc_url* :
Stores URL of server where all product images for the particular store are kept.
14. *copyright_text* :
Text which will be displayed in footer section on home page is kept here. Keep blank if not required to display copyright text in footer.
15. *client_id* :
Stores value which is generated in oauth/applications. This is used to generate valid token when customer logs in the app.
16. *client_secret* :
Stores value which is generated in oauth/applications. This is used to generate valid token when customer logs in the app.
17. *facebook_link* :
Stores link to Facebook page of the store. Keep blank if not required which will also hide Facebook icon in footer on home page.
18. *twitter_link* :
Stores link to twitter page of the store. Keep blank if not required which will also hide twitter icon in footer on home page.
19. *insta_link* :
Stores link to Instagram page of the store. Keep blank if not required which will also hide Instagram icon in footer on home page.
20. *pinterest_link* :
Stores link to Pinterest page of the store. Keep blank if not required which will also hide Pinterest icon in footer on home page.
21. *youtube_link* :
Stores link to YouTube page of the store. Keep blank if not required which will also hide YouTube icon in footer on home page.
22. *googleplus_link* :
Stores link to Google Plus page of the store. Keep blank if not required which will also hide Google Plus icon in footer on home page.
23. *support_phone* :
Stores phone number which will be displayed in contact us page.
24. *support_email* :
Stores email ID which will be displayed in contact us page.
25. *description_header* :
Stores name which will be displayed as tab header for description data in product details page.
26. *attribute_header* :
Stores name which will be displayed as tab header for attributes data in product details page.
27. *store_type* :
There can be 3 values jewelry, marketplace or blank. If type is jewelry then extra details from jewelry app is fetched. For marketplace data from marketplace app is fetched or else keep blank.
28. *currency* :
Currency symbol is stored here, which will be displayed in all price values across the app. 
39. *mobile_prefix* :
Country code which will be displayed before mobile number is kept here.
30. *size_image* :
Name of size guide image will be kept here, same will be used to fetch image from server when customer clicks on Size guide button (name stored should be same as the name of the image kept on server). If kept blank there will be no option to display size guide details in size selector.
31. *pincode_true* :
Display message if COD is available for product in product details page pin code checker. In this case customer entered pin code will have a matching pin code in pin code file with true value saved with it.
32. *pincode_false* :
Display message if COD is not available for particular product in product details page pin code checker. In this case customer entered pin code will have a matching pin code in pin code file with false value saved with it.
33. *pincode_null* :
Display message if Delivery not available for particular product in product details page. In this case customer entered pin code will have no matching pin code in pin code file. 

### String array values
Add multiple string values using **<item>** tag. 

1. *tab_keys* :
Add id which is present in product description data to be displayed in tabs in product details page.
Example: If detailed description data fetched have div with id=care and respective content inside div then tab keys one of the id stored will be *item* **care** this will create new tab in product details page which will have care details.
2. *tab_display* :
Add name to be displayed on tab header for product description data in product details page.
<aside class="notice">tab_keys and tab­­_display values are related to each other. Each entry from tab_keys corresponds to a value in tab­­_display, hence they are key-value pairs placed in two separate arrays at same indices.</aside>
3. *sort_criteria* :
Add keys which are used in api based on which sorting will be performed in product listing page.
Example:
        priority,
        price_ascending,
        price_descending,
4. *sort_display* :
Add names which will be displayed sort criteria spinner in product listing page.
<aside class="notice">*sort_criteria* and *sort­_­display* values are related to each other. Each entry from *sort_criteria* corresponds to a value in *sort_display*, hence they are key-value pairs placed in two separate arrays at same indices.</aside>
Example:
        Popular,
        Price Low-High,
        Price High-Low,
5. *category_listing* :
Add category id to this array, the sub categories of that category will be displayed in separate page before showing products.
Example:  Consider category city which will have different city names. Upon clicking city name another page will be displayed where categories will be displayed for customer to select, like brands in the particular city.
6. *menu_items* :
Pages like Terms and Condition, Shipping Details etc which needs to be shown in app, respective names should be added here which will be displayed in app drawer section below sign up.
Example:
        Terms and Condition
7. *menu_item_urls* :
Add links that is the name of the html file which is kept in assets folder.
Example:
If terms and condition data is kept in terms.html file in asset folder then name to be added here is terms
<aside class="notice">menu_items and menu­_item_urls values are related to each other.  Each entry from menu_items corresponds to a value in menu­_item_urls, hence they are key-value pairs placed in two separate arrays at same indices.</aside>
