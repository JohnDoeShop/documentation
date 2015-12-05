# category.name

Returns the name of the category.

# category.title

An alias for [name](category.md#categoryname)

# category.friendly_name

Returns the friendly name of the category.

# category.handle

An alias for [friendly_name](category.md#categoryfriendly_name)

# category.id

Returns the internal Id.

# category.default_sort_by

Returns the default sorting for the category.

# category.current_sort_by

Returns the customer selected sorting for the category.
This can be set using the `sort_by` *GET* parameter.

# category.products_price_min

Returns the price of the cheapest product in the category.

# category.products_price_max

Returns the price of the most expensive product in the category.

# category.current_price_min

Returns the current `filter by price` minimum price.  
This can be set using the `price_min` *GET* parameter.

# category.current_price_max

Returns the current `filter by price` maximum price.  
This can be set using the `price_max` *GET* parameter.

# category.all_vendors

Returns a list containing the name of all the vendor of the products in this category.

# category.current_vendor

Returns the name of the current `filter by vendor`.  
This can be set using the `vendor` *GET* parameter. 

# category.tags

Returns a list of all the tags of the products in the current category.

# category.current_tags

Returns the current `filter by tag`.  
This can be set passing a JSON array to the `tags` *GET* parameter.

# category.products

Returns a collection of [products](product.md)

The collection is filter aware.

# category.products_count

Returns the number of products in the current category, without applying any filter.

# category.depth

The depth of the current category.

# category.deep_products_count

The number of the products in the current category and all its children categories.

# category.image

Returns the image of the category.

# category.default_image

An alias for [image](category.md#categoryimage).

# category.featured_image

An alias for [image](category.md#categoryimage).

# category.url

Returns the category url.

# category.parent

Returns the parent category, if any.

# category.children

Returns a collection of children categories.
