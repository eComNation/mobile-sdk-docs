## 14. My Orders

###Files/Classes

1. MyOrdersController 
2. OrderDetailsController

###Description

Customer orders will be fetched and displayed using in a list view. Once customer will click on a particular order he/she will be taken to order details screen. This is implemented in MyOrdersController class.
Orders are fetched using the GET request to **GET ORDERS URL**.

>GET ORDERS URL:

```API
https://abcd.my39shop.com/api/v1/store/customer/orders?access_token={token_value}
```

Order Details are fetched using a GET request to **GET ORDER DETAIL URL**.

>GET ORDER DETAIL URL:

```API
https://abcd.my39shop.com/api/v1/store/customer/orders/{order_id}?access_token={token_value}
```