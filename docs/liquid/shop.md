# shop.name

Returns the shop's name.

# shop.decription

Return the shop's description.

# shop.currency_code

Returns the shop's default three-letter [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) currency code (ex: USD).

# shop.currency_symbol

Returns the shop's currency [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) symbol (ex: $).

# shop.currency_name

Returns the shop's currency name (ex: "American Dollars").

# shop.vat_id

Returns the vat id of the current shop.

# shop.domain

Returns the primary domain of the shop.

# shop.permanent_domain

Returns a `<shop-name>.<agency-domain>.com` URL of the current shop.

# shop.url

Returns the full url for the current shop

*Example*
```liquid
{{ shop.url }}
<!-- Outputs: http://www.my-shop.com -->
```

If the agency domain is not set a `<shop-name>.johndoeshop.com` domain is returned.

# shop.address

Returns the [address](address.md) of the shop

# shop.latest_products

Refer to [Machine Learning](machine-learning.md#shop.latest_products).

# shop.best_sellers

Refer to [Machine Learning](machine-learning.md#shop.best_sellers).

# shop.trending_products

Refer to [Machine Learning](machine_learning.md#shop.trending_products).

# shop.social_links

Returns a list of the shop's social networks pages.

*Example*

```liquid
{{ shop.social_links.facebook }}
<!-- Outputs: https://www.facebook.com/johndoeshop -->
```

# shop.categories_count

Returns the number of the root categories of the current shop.

# shop.deep_categories_count

Returns the number of all the categories of the current shop.

# shop.languages

Returns a list of the available languages for the current shop.

Each language has the following properties:

|Property|Sample value|
|--------|------------|
| name | Italian |
| code | it |
| url  | /set_language/it |

# shop.products_count

Returns the number of all the products for the current shop.

# shop.ship_to_countries

Returns a collection of [countries](country.md) that have at least one shipping method available. 

# shop.enabled_payment_types

Returns a list of the enabled payment processors.

*Example*
```liquid
{{ shop.enabled_payment_types }}
<!-- Outputs: ['paypal', 'braintree'] -->
```

# shop.locale

Returns the current selected locale.

Alias for [customer.locale](customer.md#customer.locale)

# shop.description

Returns the current shop's description.

# shop.name

Returns the current shop's name.

# shop.agency_name

Returns the name of the shop's agency.

# shop.agency_url

Return the url of the shop's agency.

