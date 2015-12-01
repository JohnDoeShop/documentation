# discount_code.code

Returns the discount code alphanumeric value.

# discount_code.active

Returns wheter or not the code is active and valid.

# discount_code.value

Returns the discount code value.


It represents a monetary amount if the type is `FixedAmountDiscount`.  
It represents a percentage if the type is `PercentageDiscount`.

# discount_code.amount

An alias for [value](discount-code.md#discount_code.amount)

# discount_code.savings

The same as [value](discount-code.md#discount_code.value), but with a negative sign.

# discount_code.type

Returns the type of the discount code, can be either:

`PercentageDiscount`: The discount is proportional to the total amount of the cart.  
`FixedAmountDiscount`: The discount has a fixed monetary value.

# discount_code.free_shipping

When this value is `true` the [shipping costs](cart.md#cart.shipping_price) are 0.  
This just means that this discount code entitles the customer to have its products shipped for free.
