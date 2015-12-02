# Cart review

## Liquid tags

* `checkout_flow`: true
* `checkout_step`: 1

## Request

* Method: `GET`
* URL: `/cart`
---
# Shipping details

## Liquid tags

* `checkout_flow`: true
* `checkout_step`: 2

## Request

* Method: `GET` `POST`
* URL: `/checkout`
---
# Payment

## Liquid tags

* `checkout_flow`: true
* `checkout_step`: 3

## Request

* Method: `POST`
* URL: `/cart/payment`
* Parameters:
    * `checkout[shipping_address][first_name]`
    * `checkout[shipping_address][last_name]`

** NOTE: ** Do *not* in any way for any reason try to modify the standard behaviour of the payment buttons. The payment buttons are meant to be PCI DSS compliant, and you cannot modify them.  
If you find there is some problem with these buttons, or you have any request please don't hesitate to contact us.
---
# Order completed

## Liquid tags

* `checkout_flow`: true
* `checkout_step`: 4
* `order`

## Request

* Method: `GET`
* URL: `/cart/payment_success` `/cart/payment_failed`
* Parameters:
     * `email`
     * `order`

## Parameters

* `email`: The email associated to the order 
* `order`: Can be both the [order internal Id](order.md#orderid) or the [order counter](order.md#ordercounter) without any prefix or suffix.


