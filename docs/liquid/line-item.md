# line_item.product

Returns the [product](product.md) associated with the line item.  
This value is `nil` if the product has one or more [variants](variant.md)

# line_item.product_or_variant

If the [product](product.md) associated with the current item has a [variant](variant.md), the selected variant is returned.  
Otherwise product itself is returned.

# line_item.default_image

Returns the default image for this line item.

*Example*
```liquid
{{ line_item.default_image }}
<!-- Outputs the master image: //az763220.vo.msecnd.net/[...]/product-[...]-master -->

{{ line_item.default_image | img_url: 'medium' }}
<!-- Outputs the medium size image: //az763220.vo.msecnd.net/[...]/product-[...]-medium -->
```
 
# line_item.featured_image

An alias for [default_image](line-item.md#line_itemdefault_image)

# line_item.id

The line item internal Id.

# line_item.product_name

Always return the name of the base [product](product.md).

```liquid
{{ line_item.product_name }}
<!-- Outputs: Samsung Galaxy S8 -->
```

# line_item.variant_name

Returns the name of the current [variant](variant.md) if any.

*Example*

```liquid
{{ line_item.variant_name }}
<!-- Outputs: 25GB • Black -->
```

# line_item.product_url

Returns the url of the base [product](product.md) or the selected variant.

# line_item.product_compare_at_price

Returns the compare at price of the [base product](product.md) or the [selected variant](variant.md).

# line_item.product_price

Returns the price of the [base product](product.md) or the [selected variant](variant.md).

# line_item.line_compare_at_price

Returns the `compare at price` of the line item.  
It is the [product compare at price](line-item.md#line_itemproduct_compare_at_price) multiplied by the [quantity](line-item.md#line_itemquantity).

*Example*
```liquid
{{ line_item.product_compare_at_price }}
<!-- Outputs: 12 -->

{{ line_item.quantity }}
<!-- Outputs: 8 -->

{{ linet_item.line_compare_at_price }}
<!-- Outputs: 96 -->
```

# line_item.line_price

Retunrs the total price of the line.
It is the [product price](line-item.md#line_itemproduct_price) muliplied by the quantity.

# line_item.quantity

Returns the quantity of the selected [product](product.md)

