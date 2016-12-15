# 1. Android Store App Documentation

## 1. Pre-requisites
<ul>
<li> An xml file, named as config.xml, is used to store important data regarding the store. This data includes store related URLs, keys, app color values, settings to enable/disable optional features throughout the app.</li>
<li> A base URL which points to the app server which is used for all API requests to fetch and send the data to and from the sever.
For example, a store with name “ABCD” will have a server URL of the form,
<b>https://abcd.my39shop.com/</b></li>
The same will be used in all sample API call URLs in this document.
<li> A store can be of three types, which depends on the use of extra API calls to get additional product data in the product detail screen.
<ul>
<li> A normal store only needs the base URL for all its operations.</li>
<li> A Jewelry store app requires an additional call to the jewelry app server. The URL is, <b>http://jewelcommerce.my39shop.com/</b></li>
<li> A market place app requires an additional call to the market place server. The URL is,<b>http://marketplace.my39shop.com/</b></li>
</ul></li>
<li> To register ratings and reviews for products we use reviews app. The URL is,
<b>http://reviews.my39shop.com/</b></li>
<li> Throughout the app Gson library is used to serialize and deserialize Java objects to (and from) JSON. All the APIs return a JSON string response which is then converted into java objects using an instance of Gson.</li>
<li> Volley library is used throughout the app to make API calls. Five different methods, namely GET, PUT, PATCH, POST and DELETE are used for different data operations. These methods are written at a common location and then used from different screens using an instance of a CallBack interface to return the response of the API request to its calling screen.</li>
<li> Picasso library is used for all image related operations through the app.</li>
<li> Throughout the app the data is shared among screens using the shared preferences. For example a local copy of customer’s cart is maintained in the shared preferences, which is later used in various screens to display cart count and also in cart screen to display the content of the cart.</li>
</ul>
