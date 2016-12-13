# 2. iOS Store App Documentation

## 1. Pre-requisites

1. An swift file, named as AppConfig.swift, is used to store important data regarding the store. This data includes store related URLs, keys, app color values, settings to enable/disable optional features throughout the app.
2. A base URL which points to the app server which is used for all API requests to fetch and send the data to and from the sever.
For example, a store with name “ABCD” will have a server URL of the form,
**https://abcd.my39shop.com/**
The same will be used in all sample API call URLs in this document.
3. A store can be of three types, which depends on the use of extra API calls to get additional product data in the product detail screen.
* A normal store only needs the base URL for all its operations.
* A Jewelry store app requires an additional call to the jewelry app server. The URL is, **http://jewelcommerce.my39shop.com/**
* A market place app requires an additional call to the market place server. The URL is,**http://marketplace.my39shop.com/**
4. To register ratings and reviews for products we use reviews app. The URL is,
**http://reviews.my39shop.com/**
5. Throughout the app the data is shared among screens using the persistency manager. For example a local copy of customer’s cart is maintained in the persistency store, which is later used in various screens to display cart count and also in cart screen to display the content of the cart.
