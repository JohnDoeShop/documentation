# Basics

This is an introduction to Liquid. You can find the original [here](https://docs.shopify.com/themes/liquid-documentation/basics)

## Introduction
We choose to use Liquid as our default template engine to be as compatible as possible with Shopify's syntax.
Many of you already used Shopify to design a frontend so we tried to be consistent with their variables, objects and filters so you don't need to learn a completely new syntax.

Liquid uses a combination of tags, objects, and filters to load dynamic content. They are used inside Liquid template files, which are a group of files that make up a theme. 

### Tags

Tags make up the programming logic that tells templates what to do. 
```liquid
{% if user.name == 'John Doe' %}
  Hey John!
{% endif %}
```

### Objects

Objects contain attributes that are used to display dynamic content on the page. 

```liquid
{{ product.title }} <!-- Output: Awesome T-Shirt-->
```

### Filters

Filters are used to modify the output of strings, numbers, variables, and objects. 

```liquid
{{ 'sales' | append: '.jpg' }} <!-- Output: sales.jpg -->
```

## Operators

Liquid has access to all of the logical and comparison operators. These can be used in tags such as if and unless. 

### Basic Operators

| Operator | Meaning |
|--|------------------------|
| == |  equals                |
| != |  does not equal        |
| > |  greater than          |
| < |  less than             |
| >= |  greater than or equal |
| < |  less than or equal    |
| and |   A and B             |
| or |  A or B                |

*Examples*

```liquid
{% if product.title == "Awesome Shoes" %}
    These shoes are awesome!
{% endif %}
```

Operators can be chained together. 

```liquid
{% if product.type == "Shirt" or product.type == "Shoes" %}
    This is a shirt or a shoe. 
{% endif %}
```

### Contains

`contains` checks for the presence of a substring inside a string. 

```liquid
{% if product.title contains 'Pack' %}
  This product's title contains the word Pack.
{% endif %}
```

`contains` can also check for the presence of a string in an array of strings.

```liquid
{% if product.tags contains 'Hello' %}
  This product has been tagged with 'Hello'.
{% endif %}
```

You cannot check for the presence of an object in an array of objects using contains. This will not work:

```liquid
{% if product.category contains 'T-Shirts' %}
  This product belongs to the T-shirts category.
{% endif %}
```

## Types

Liquid objects can return one of five types: String, Number, Boolean, Nil or Array. Liquid variables can be initialized by using the assign or capture tags. 

### Strings

Strings are declared by wrapping the variable's value in single or double quotes. 

```liquid
{% assign my_string = "Good Morning" %}
```

### Numberical

Numbers include floats and integers. 

```liquid
{% assign my_num = 25 %}
```

### Booleans 

Booleans are either true or false. No quotations are necessary when declaring a boolean.

```liquid
{% assign foo = true %}
{% assign bar = false %}
```

### Nil


`nil` is an empty value that is returned when Liquid code has no results. It is not a string with the characters "nil".

`nil` is treated as false in the conditions of `{% if %}` blocks and other Liquid tags that check for the truthfulness of a statement. The example below shows a situation where a fulfillment does not yet have a tracking number entered. The if statement would not render the included text within it. 

```liquid
{% if fulfillment.tracking_numbers %}
We have a tracking number!
{% endif %}
```

Any tags or outputs that return nil will not show anything on the screen. 

### Arrays

Arrays hold a list of variables of all types. 

##### Accessing all items in an array

To access items in an array, you can loop through each item in the array using a for tag or a tablerow tag. 

```liquid
<!-- if product.tags = "sale", "summer", "spring", "wholesale" -->
{% for tag in product.tags %}
    {{ tag }}
{% endfor %}
```

##### Accessing a specific item in an array

You can use square brackets ( [ ] ) notation to access a specific item in an array. Array indexing starts at zero. 

```liquid
<!-- if product.tags = "sale", "summer", "spring", "wholesale" -->
{{ product.tags[0] }} 
{{ product.tags[1] }} 
{{ product.tags[2] }} 
{{ product.tags[3] }}
```

##### Initializing an array

It is not possible to initialize an array in Liquid. For example, in Javascript you could do something like this: 

```liquid
<script>
var songs = ["Lost in the World", "Mercy", "Gold Digger", "Runaway"];
</script>
```

In Liquid, you must instead use the split filter to break a single string into an array of substrings. See split for examples. 

## Truthy and Falsy

# What is liquid?

In programming, we describe “truthy” and “falsy” as anything that returns true or false, respectively, when used inside an if statement. 

## What is true?

All values in Liquid are truthy, with the exception of nil and false.

In the example below, the text “John Doe” is not a boolean, but it is truthy in a conditional: 

```liquid
{% assign john_doe = 'John Doe' %}
{% if john_doe %}
This will always be true.
{% endif %}
```
Strings, even when empty, are truthy. The example below will result in empty HTML tags if `settings.body_background` is defined but empty: 

```liquid
{% if settings.body_background %}
<h1>{{ settings.body_background }}</h1>
{% endif %}
<!-- Output: <h1></h1> -->
```

## What is false?

The only values that are falsy in Liquid are nil and false.

`nil` is returned when a Liquid object doesn't have anything to return. For example, if a category doesn't have an image, category.image will be set to nil. Since that is falsy, you can do this: 

```liquid
{% if category.image %}
<!-- Output: //az763220.vo.msecnd.net/... (category image if present) -->
{% endif %}
```

The value false is returned through many Liquid object properties such as `product.available`, and others. 

