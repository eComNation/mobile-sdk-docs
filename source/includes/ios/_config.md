## 2. AppConfig File

AppConfig file is an swift file containing different store related values in boolean, color, dimensions, string, string arrays.

### Boolean values

1.	*ShowDetailsTab*:
Product filter attribute details as key value pairs will be shown in product descriptions tabs in product details page if set true. 
2.	*ShowLoaderIcon*:
In product listing page store logo icon will be displayed instead of progress bar until product image is loading.
3.	*EnableOutOfStock*:
If set true, “Out Of Stock” label is shown in the in product listing screen for individual products.
4.	*EnableDiscountListing*:
If set true, shows discount percentage value instead of a sale label for individual products in product listing screen.
5.	*IsPinCodeCheckEnabled*:
If set true, product detail screen shows a pin code checker for order delivery locations.

### Dimension values

1. *SidePanelSize* :
Drawer width in home page is set using this value. Value ranges from 180dp to 320dp, set depending on text length displayed in drawer.

### Color values

1. *BaseApplicationColor* :
App header color is set using this value throughout the application.
2. *FadedApplicationColor* :
If tabs are present in home screen then the tab header text color which is not selected is set using this value. Generally this color is set either darker or lighter shade of primary color.
3. *GeneralButtonColor* :
This color is used as background color of all button, number of cart items displayed in header and also favorite icon when a particular product is added to favorite list. Also this color is used as text color which acts as a clickable link.
4. *ClickedButtonColor* :
Generally this color is darker or lighter shade of secondary color, used as background of buttons in clicked mode.
5. *SidePanelTextColor* :
Text which is displayed on app drawer is set using this color value.
6. *SidePanelCellColor* :
Sets background color of app drawer items in home page.
7. *SidePanelBGColor* :
Background color behind store logo in app drawer is set using this color value.
8. *FooterColor* :
Footer background color in home page is set using this color value.
9. *CopyrightTextColor* :
Copyright text shown in footer uses this color value.

###String values

1.	*StoreId*:
It is the store id associated with each store.
2.	*FacebookSignInClientId*:
Facebook id which we get when app is created on Facebook developers page with which we can use Log In with Facebook feature.  If kept blank then Facebook button will not be visible in Log In page.
3.	*GoogleSignInClientId*:
Google id which we get when app is created in Google developers page with which we can use Log In with Google feature.  If kept blank then Google button will not be visible in Log In page.
4.	*ProductShareURL*:
Product URL of the store where all products are displayed.  This is used when customer shares a particular product to other customers.
Example:  abc.com/products/
5.	*BaseServiceURL*:
Stores URL of the store. This is used for API requests to fetch respective data.
Example: http:// abc.my39shop.com/
6.	*ApplicationName*:
Stores name of the app or store name.
7.	*PincodeURL*:
Stores URL of the file where all pin code values are stored. If kept blank then the pin code checker functionality is disabled product details page.
8.	*ProductColor*:
Stores URL of server where all product images for the particular store are kept.
9. *CopyrightText*:
Text which will be displayed in footer section on home page is kept here. Keep blank if not required to display copyright text in footer.
10.	*ApplicationClientId*:
Stores value which is generated in oauth/applications. This is used to generate valid token when customer logs in the app.
11.	*ApplicationClientSecret*:
Stores value which is generated in oauth/applications. This is used to generate valid token when customer logs in the app.
12.	*ApplicationFBLink*:
Stores link to Facebook page of the store. Keep blank if not required which will also hide Facebook icon in footer on home page.
13.	*ApplicationTwitterLink*:
Stores link to twitter page of the store. Keep blank if not required which will also hide twitter icon in footer on home page.
14.	*ApplicationInstagramLink*:
Stores link to Instagram page of the store. Keep blank if not required which will also hide Instagram icon in footer on home page.
15.	*ApplicationPinterestLink*:
Stores link to Pinterest page of the store. Keep blank if not required which will also hide Pinterest icon in footer on home page.
16.	*ApplicationYoutubeLink*:
Stores link to YouTube page of the store. Keep blank if not required which will also hide YouTube icon in footer on home page.
17.	*ApplicationGPlusLink*:
Stores link to Google Plus page of the store. Keep blank if not required which will also hide Google Plus icon in footer on home page.
18.	*ContactPhone*:
Stores phone number which will be displayed in contact us page.
19.	*ContactMail*:
Stores email ID which will be displayed in contact us page.
20.	*StoreType*:
There can be 3 values jewelry, marketplace or blank. If type is jewelry then extra details from jewelry app is fetched. For marketplace data from marketplace app is fetched or else keep blank.

### String array values
Add multiple string values to these arrays. 

1. *sort_criteria* :
Add keys which are used in api based on which sorting will be performed in product listing page.
Example:
        priority,
        price_ascending,
        price_descending,
2. *sort_display* :
Add names which will be displayed sort criteria spinner in product listing page.
<aside class="notice">*sort_criteria* and *sort­_­display* values are related to each other. Each entry from *sort_criteria* corresponds to a value in *sort_display*, hence they are key-value pairs placed in two separate arrays at same indices.</aside>
Example:
        Popular,
        Price Low-High,
        Price High-Low,
3. *categoryListing* :
Add category id to this array, the sub categories of that category will be displayed in separate page before showing products.
Example:  Consider category city which will have different city names. Upon clicking city name another page will be displayed where categories will be displayed for customer to select, like brands in the particular city.
