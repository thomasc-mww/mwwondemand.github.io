# Errors

The MWW API relies on the following error conditions:

## UnauthorizedError
Error Code | Meaning
---------- | -------
401 | UNAUTHORIZED

**Title**

'Authorized Users Only'

**Description**

The requestor is unauthorized to act on the requested resource.


## ProductCodeError
Error Code | Meaning
---------- | -------
100 | VALIDATION_ERROR

**Title**

'Product code not valid.'

**Description**

The product code is incorrect, see the line number indicated in your order.


## UpdateShippingAddressError
Error Code | Meaning
---------- | -------
422 | UNPROCESSABLE_ENTITY

**Title**

'Cannot update shipping address'

**Description**

The order has already shipped. It is no longer possible to change the shipping address for this order.

**Notes**

'The 422 (Unprocessable Entity) status code means the server understands the content type of the request entity, and the syntax of the request entity is correct (thus a 400 (Bad Request) status code is inappropriate) but was unable to process the contained instructions.'

[https://tools.ietf.org/html/rfc4918#section-11.2](https://tools.ietf.org/html/rfc4918#section-11.2)


## MissingShippingAddressError
Error Code | Meaning
---------- | -------
422 | UNPROCESSABLE_ENTITY

**Title**

'Shipping address is required'

**Description**

The order is missing a shipping address. A shipping request is required to submit an order.

**Notes**

'The 422 (Unprocessable Entity) status code means the server understands the content type of the request entity, and the syntax of the request entity is correct (thus a 400 (Bad Request) status code is inappropriate) but was unable to process the contained instructions.'

[https://tools.ietf.org/html/rfc4918#section-11.2](https://tools.ietf.org/html/rfc4918#section-11.2)


## InvalidOrderFormatError
Error Code | Meaning
---------- | -------
422 | UNPROCESSABLE_ENTITY

**Title**

'Invalid Order Format'

**Description**

Please ensure that the item designs are an array

**Notes**

'The 422 (Unprocessable Entity) status code means the server understands the content type of the request entity, and the syntax of the request entity is correct (thus a 400 (Bad Request) status code is inappropriate) but was unable to process the contained instructions.'

[https://tools.ietf.org/html/rfc4918#section-11.2](https://tools.ietf.org/html/rfc4918#section-11.2)

## InvalidShippingAddressError
Error Code | Meaning
-----------|--------
422 | UNPROCESSABLE_ENTITY

**Title**

'Invalid Shipping Address'

**Description**

Please ensure that a valid shipping address is provided.

**Notes** 

'The 422 (Unprocessable Entity) status code means the server understands the content type of the request entity, and the syntax of the request entity is correct (thus a 400 (Bad Request) status code is inappropriate) but was unable to process the contained instructions.'

[https://tools.ietf.org/html/rfc4918#section-11.2](https://tools.ietf.org/html/rfc4918#section-11.2)

## IncompleteShippingAddressError
Error Code | Meaning
-----------|--------
422 | UNPROCESSABLE_ENTITY

**Title**

'Incomplete Shipping Address'

**Description**

Please ensure that all fields for the shipping address were provided

**Notes** 

'The 422 (Unprocessable Entity) status code means the server understands the content type of the request entity, and the syntax of the request entity is correct (thus a 400 (Bad Request) status code is inappropriate) but was unable to process the contained instructions.'

[https://tools.ietf.org/html/rfc4918#section-11.2](https://tools.ietf.org/html/rfc4918#section-11.2)

## LineItemQuantityError
Error Code | Meaning
-----------| -------
422 | UNPROCESSABLE_ENTITY

**Title**

'Line Item Quantity not valid'

**Description**

Cannot have a quantity of (insert_quantity_here), see respective line number of your order.

**Notes** 

'The 422 (Unprocessable Entity) status code means the server understands the content type of the request entity, and the syntax of the request entity is correct (thus a 400 (Bad Request) status code is inappropriate) but was unable to process the contained instructions.'

[https://tools.ietf.org/html/rfc4918#section-11.2](https://tools.ietf.org/html/rfc4918#section-11.2)

##LineItemLineNumberError
Error Code | Meaning
-----------| -------
422 | UNPROCESSABLE_ENTITY

**Title**

'Line Item Line Number not valid'

**Description**

The line number must be less than or equal to 9999 and unique to the order.

**Notes** 

'The 422 (Unprocessable Entity) status code means the server understands the content type of the request entity, and the syntax of the request entity is correct (thus a 400 (Bad Request) status code is inappropriate) but was unable to process the contained instructions.'

[https://tools.ietf.org/html/rfc4918#section-11.2](https://tools.ietf.org/html/rfc4918#section-11.2)

## DuplicateVendorPoError
Error Code | Meaning
-----------| -------
422 | UNPROCESSABLE_ENTITY

**Title**

'Vendor Po must be unique'

**Description**

The provided vendor PO has already been submitted for this user. Vendor PO must be unique.

**Notes** 

'The 422 (Unprocessable Entity) status code means the server understands the content type of the request entity, and the syntax of the request entity is correct (thus a 400 (Bad Request) status code is inappropriate) but was unable to process the contained instructions.'

[https://tools.ietf.org/html/rfc4918#section-11.2](https://tools.ietf.org/html/rfc4918#section-11.2)

## FutureShipDateError
Error Code | Meaning
-----------| -------
422 | UNPROCESSABLE_ENTITY

**Title**

'Future Ship Date not valid'

**Description**

Future Ship Date: The ship date provided is before the current date.

**Notes** 

'The 422 (Unprocessable Entity) status code means the server understands the content type of the request entity, and the syntax of the request entity is correct (thus a 400 (Bad Request) status code is inappropriate) but was unable to process the contained instructions.'

[https://tools.ietf.org/html/rfc4918#section-11.2](https://tools.ietf.org/html/rfc4918#section-11.2)


## InternalServerError
Error Code | Meaning
---------- | -------
500 | INTERNAL_SERVER_ERROR

**Title**

'Internal Server Error'

**Description**

This is a standard HTTP error

**Notes**
'The server encountered an unexpected condition which prevented it from fulfilling the request.'

[https://tools.ietf.org/html/rfc2616#section-10.5.1](https://tools.ietf.org/html/rfc2616#section-10.5.1)
