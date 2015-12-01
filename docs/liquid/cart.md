# cart.customer_notes

Returns the notes the customer left for the merchant.

# cart.shipping_address

Returns the [shipping address](address.md) of the current cart.

# cart.billing_address

Returns the [billing address](address.md) of the current cart.

# cart.shipping_methods

Returns a collection of [shipping methods](shipping-method.md) available for the current cart.

# cart.shipping_method

Returns the selected [shipping method](shipping-method.md) of the current cart.

# cart.discount_code

Returns the [discount code](discount-code.md) associated to the current cart.

Returns nil if no discount code is associated.

# cart.discount_code_value

Returns the monetary value of the discount code, always <= 0.

# cart.different_billing_address

Wheter the [billing address](address.md) is different from the shipping address for the current cart.

# cart.item_count

The number of the [line items](line-item.md) present in the current cart.

# cart.total_quantity

The total number of products in the current cart.

# cart.line_items

Returns a collection of [line items](line-item.md) for the current cart.

# cart.items_price_without_discount

Returns the value of the products without applying any [discount code](discount-code.md)

# cart.items_price

Returns the value of the products minus the value of the discount code when applicable.

# cart.shipping_price

Returns the price of the selected shipping method.

# cart.total_price

Returns the grand total of the current cart.

# cart.total_weight

Returns the total weight of the cart in Kilograms.

