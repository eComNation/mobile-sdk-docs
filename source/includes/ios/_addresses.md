## 15. Addresses

###Files/Classes

1. MyAddressesController
2. AddAddressController

###Description

Customer’s saved addresses are displayed here. There is an option to add a new address, update or delete an existing address. This is implemented in the AddressesActivity class. A maximum of 5 addresses can be added. 
To add and update an address AddAddressController class is used.
All addresses are fetched using a GET request to **GET ADDRESSES URL**.

<aside class="notice">
GET ADDRESSES URL:<br/>
https://abcd.my39shop.com/api/v1/store/customer/addresses?access_token={token_value}
</aside>

>GET ADDRESSES URL RESPONSE:

```json
{
	"addresses":[{
		"id":30882,
		"first_name":"chetan",
		"last_name":"kumar",
		"address1":"Tivrem",
		"address2":"Marcela",
		"city":"Ponda",
		"state_id":62,
		"state_name":"Goa",
		"country_id":99,
		"country_name":"India",
		"zipcode":"403107",
		"phone":"9696969696"}]
}
```

An address is deleted using DELETE request **DELETE ADDRESS URL**.

<aside class="notice">
DELETE ADDRESS URL:<br/>
https://abcd.my39shop.com/api/v1/store/customer/addresses/{address_id_value}?access_token={token_value}
</aside>

>DELETE ADDRESS URL RESPONSE:

```json
{"result":"success"}
```

An address is fetched using GET request to **GET ADDRESS URL**.

<aside class="notice">
GET ADDRESS URL:<br/>
https://abcd.my39shop.com/api/v1/store/customer/addresses/{address_id_value}?access_token={token_value}
</aside>

>GET ADDRESS URL RESPONSE:

```json
{
	"address":{
		"id":30882,
		"first_name":"chetan",
		"last_name":"kumar",
		"address1":"Tivrem",
		"address2":"Marcela",
		"city":"Ponda",
		"state_id":62,
		"state_name":"Goa",
		"country_id":99,
		"country_name":"India",
		"zipcode":"403107",
		"phone":"9696969696"
	}
}
```

A new address is created using a POST request to **NEW ADDRESS URL**.

<aside class="notice">
NEW ADDRESS URL:<br/>
https://abcd.my39shop.com/api/v1/store/customer/addresses?first_name={firstname_value}&last_name={lastname_value}&phone={phone_value}&address1={address1_value}&address2={address2_value}&country_id={country_id_value}&state_id={state_id_value}&city={city_value}&zipcode={zipcode_value}&access_token={token_value}
</aside>

>NEW ADDRESS URL RESPONSE:

```json
{
	"address":{
		"id":30882,
		"first_name":"chetan",
		"last_name":"kumar",
		"address1":"Tivrem",
		"address2":"Marcela",
		"city":"Ponda",
		"state_id":62,
		"state_name":"Goa",
		"country_id":99,
		"country_name":"India",
		"zipcode":"403107",
		"phone":"9696969696"
	}
}
```

An existing address is updated using PUT request to **UPADTE ADDRESS URL**.

<aside class="notice">
UPDATE ADDRESS URL:<br/>
https://abcd.my39shop.com/api/v1/store/customer/addresses/{address_id_value}? first_name={firstname_value}&last_name={lastname_value}&phone={phone_value}&address1={address1_value}&address2={address2_value}&country_id={country_id_value}&state_id={state_id_value}&city={city_value}&zipcode={zipcode_value}&access_token={token_value}
</aside>

>UPDATE ADDRESS URL RESPONSE:

```json
{
	"address":{
		"id":30882,
		"first_name":"chetan",
		"last_name":"kumar",
		"address1":"Orgao",
		"address2":"Marcela",
		"city":"Ponda",
		"state_id":62,
		"state_name":"Goa",
		"country_id":99,
		"country_name":"India",
		"zipcode":"403107",
		"phone":"9696969696"
	}
}
```