## 5. Filters

### Files/Classes
1. FilterActivity

### Description

The filter attributes fetched at app start up are used in the filters screen, which returns all the attributes with attribute indices as key-value pairs. When product listing is opened the products will either belong to a category or a result of a search query. So when customer opens the filter screen we need to only show those attributes that are relevant to the current collection of products.

For doing this, as explained above, we need to make a call to the same API (first call) that was called for either category listing or a search query with just a single change in the parameters. The parameters *facets* is by default false in the first call and then we have sent it as true in the second call without changing any other parameter. This returns a list of attribute indices that are relevant to the current list of products, using which we can hide the non –relevant attributes.

Once the customer selects the filters make a GET request using the same API with an extra parameter called *filter_attributes* and its value should be a comma separated string of all the selected filter attribute indices.
