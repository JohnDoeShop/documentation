# Usage

The javascript library is included by default in your page and is loaded by the `{{ content_for_header }}` tag.  
If you don't want to use the javascript library just add 'no-scripts' as an argument like this: `{{ content_for_header: 'no-scripts' }}`

However we highly recommend to use the library.

# Carts

Whenever a product is added, removed or its quantity is updated from the cart, the javascript library automatically reloads all the carts in the page.

There are three built in carts:

| Name | Endpoint URL | HTML Data Attribute | Usage |
| -- | -- | -- | -- |
| Cart full | /cart/full.ajax | data-cart-full | Should be used during the [cart review](checkout.md) phase of the checkout |
| Cart mini | /cart/mini.ajax | data-cart-mini | You can use this cart as a preview in the navigation bar |
| Cart additional | /cart/additional.ajax | data-cart-additional | An additional cart you can use in your pages |

What happen behind the scenes on an update:  

* The library checks how many carts there are on the page  
* The library downloads the new carts from the respective endpoints  
* The library replaces any HTML element containing a `data-cart-*` attribute with the new cart.

This way you don't have to worry about manually synching all the carts on your page.

# Add to cart

The javascript library makes it easy to add a produt to the cart.

To add a product we need to send a *POST* request to `/cart/add` as documented [here](endpoints.md).  
This would be easily done with a simple HTML `form`, but to create a seamless experience for the user, and to make it simpler to implement we can use the javascript library.

Consider the code below:
```liquid
<form action="/cart/add" method="post">
  <input type="hidden" name="product" value="{{ product.id }}" />
  <input type="submit" value="Add to Cart" />
</form>
```

This is the simplest add to cart button you can imagine.  
What happen behind the scenes:

* The library adds the *CSRF token* to the form
* The library prevents the form from submitting
* The library sends an *AJAX* request to `/cart/add`
* The library decides wheter to show a popup, or do nothing

Unfortunately this is not always the case.
Sometime we need to handle product with variants, or add more than one item:
```liquid
<form action="/cart/add" method="post">
  {% if product.has_variants %}
    <input type="hidden" name="variant" value="{{ product.selected_or_first_available_variant.id }}" />
  {% endif %}
  <input type="hidden" name="product" value="{{ product.id }}" />
  <input type="text" name="quantity" />
  <input type="submit" value="Add to Cart" />
</form>
```

# Add to cart popup

After we successfully added a product to the cart we can decide to show the user a popup.

As usual the javascript library comes handy.

The only thing we need is to add some code in the `/cart/popup.ajax` template.

*Example*

```liquid
<div>
  You have just add {{ line_item.product_name }} to the cart.

  <a href="/cart">Checkout</a>
  <span data-close-popup>Continue shopping</span>
</div>
```

Other common behaviours after an add to cart:

* Show a popup
* Do nothing
* Redirect to the cart

## Show a popup 

To shop a popup insert your HTML in the `/cart/popup.ajax`, your element will be shown in the middle of the page.

Any element with a `data-close-popup` will close the popup on click.

## Do nothing

Quite simple, just leave the `/cart/popup.ajax` template completely empty.

## Redirect to cart

This is a bit tricky, so you can just copy-paste the code below in the `/cart/popup.ajax` template:
```liquid
<style>
    .popup_add_to_cart_invisible { 
        background: rgba(0, 0, 0, 0);
    }
</style>
<script>
    window.location.href = '/cart';
</script>
```

