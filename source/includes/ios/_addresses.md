## 15. Addresses

###Files/Classes

1. MyAddressesController
2. AddAddressController

###Description

Customer’s saved addresses are displayed here. There is an option to add a new address, update or delete an existing address. This is implemented in the AddressesActivity class. A maximum of 5 addresses can be added. 
To add and update an address AddAddressController class is used.
All addresses are fetched using a GET request to **GET ADDRESSES URL**.

>GET ADDRESSES URL:

```API
https://abcd.my39shop.com/api/v1/store/customer/addresses?access_token={token_value}
```

An address is deleted using DELETE request **DELETE ADDRESS URL**.

>DELETE ADDRESS URL:

```API
https://abcd.my39shop.com/api/v1/store/customer/addresses/{address_id_value}?access_token={token_value}
```

An address is fetched using GET request to **GET ADDRESS URL**.

>GET ADDRESS URL:

```API
https://abcd.my39shop.com/api/v1/store/customer/addresses/{address_id_value}?access_token={token_value}
```

A new address is created using a POST request to **NEW ADDRESS URL**.

>NEW ADDRESS URL:

```API
https://abcd.my39shop.com/api/v1/store/customer/addresses?first_name={firstname_value}&last_name={lastname_value}&phone={phone_value}&address1={address1_value}&address2={address2_value}&country_id={country_id_value}&state_id={state_id_value}&city={city_value}&zipcode={zipcode_value}&access_token={token_value}
```

An existing address is updated using PUT request to **UPADTE ADDRESS URL**.

>UPDATE ADDRESS URL:

```API
https://abcd.my39shop.com/api/v1/store/customer/addresses/{address_id_value}? first_name={firstname_value}&last_name={lastname_value}&phone={phone_value}&address1={address1_value}&address2={address2_value}&country_id={country_id_value}&state_id={state_id_value}&city={city_value}&zipcode={zipcode_value}&access_token={token_value}
```
