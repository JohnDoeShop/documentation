# link.active

Returns true if the current page is the one pointed by the link.

# link.object

Returns the object pointed by this link.

It is only applicable for the following types:

* `page_link`
* `category_link`
* `product_link`
* `article_link`

# link.name

Returns the name of the link.

# link.title

An alias for [name](link.md#link.name).

# link.type

Returns the type of the link.

Possible values:

|Return value|Meaning|
| -- | -- |
| homepage_link | The link will point to `/` |
| category_link | The link points to a category |
| product_link | The link points to a product |
| page_link | The link points to a page |
| blog_link | The link points to blog |
| social_link | The link points to a social network page of the [shop](shop.md) |
| article_link | The link points to a blog post |
| http_link | The link points to a specific url |

# link.url

Returns the url pointed by this link.
