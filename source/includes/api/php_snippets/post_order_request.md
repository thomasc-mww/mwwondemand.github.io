```php
<?php

// Get cURL resource
$ch = curl_init();

// Set url
curl_setopt($ch, CURLOPT_URL, 'https://api.mwwondemand.com/api/orders');

// Set method
curl_setopt($ch, CURLOPT_CUSTOMREQUEST, 'POST');

// Set options
curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);

// Set headers
curl_setopt($ch, CURLOPT_HTTPHEADER, [
  "Content-Type: application/vnd.api+json",
  "Authorization: auth-key=YOUR_API_KEY",
  "Accept: application/vnd.api+json; version=1",
 ]
);
// Create body
$body = '{"data": {
   "type": "orders",
   "attributes": {
     "vendor-po": "1467988109",
     "shipping-method": "SAMPLE",
     "shipping-account-number": "1234",
   }
 },
 "included": [
   {
     "type": "shipping-address",
     "attributes": {
     "name": "Phillip J. Fry",
       "address1": "123 Green St.",
       "address2": "Suite 321",
       "city": "New New York",
       "state": "NY",
       "country": "US",
       "postal-code": "10012",
       "email": "bob@dobalina.net",
       "phone": "8288888888"
     }
   },
   {
     "type": "billing-address",
     "attributes": {
       "name": "Hubert Farnsworth",
       "address1": "123 Green St.",
       "address2": "Suite 321",
       "city": "New New York",
       "state": "NY",
       "country": "US",
       "postal-code": "10012",
       "email": "bob@dobalina.net",
       "phone": "8288888888"
     }
   },
   {
     "type": "line-items",
     "attributes": {
       "line-number": 1,
       "quantity": 2,
       "description": "It\'s not sò fluffy!",
       "product-code": "3PF-SC6-SPFPI",
       "customer-product-code": "YOUR_UPC/SKU_NUMBER",
       "item-properties": {
         "thread-color": "white",
         "hs-code": "1234.56.789" 
       },
       "designs": [
         {
           "image-remote-url": "https://static.pexels.com/photos/39803/pexels-photo-39803.jpeg"
         }
       ]
     }
   },
   {
     "type": "line-items",
     "attributes": {
       "line-number": 2,
       "quantity": 5,
       "description": "Velour Vest",
       "product-code": "3PF-SC6-SPFPI",
       "customer-product-code": "YOUR_UPC/SKU_NUMBER",
       "item-properties": {
         "thread-color": "white",
         "hs-code": "1234.56.789"
       },
       "designs": [
         {
           "image-remote-url": "http://www.publicdomainpictures.net/pictures/10000/velka/orange-871282749123hSB3.jpg"
         }
       ]
     }
   },
   {
     "type": "packing-list",
     "attributes": {
       "url": "https://dllc.appstate.edu/sites/dllc.appstate.edu/files/SearchCCimages.pdf"
      }
     },
     {
     "type": "shipping-label",
     "attributes": {
      "url": "https://upload.wikimedia.org/wikipedia/commons/0/04/Einschreiben-Label_Deutsche_Post_2011.jpg"
     }
   }
 ]}';

// Set body
curl_setopt($ch, CURLOPT_POST, 1);
curl_setopt($ch, CURLOPT_POSTFIELDS, $body);

// Send the request & save response to $resp
$resp = curl_exec($ch);

if(!$resp) {
  die('Error: "' . curl_error($ch) . '" - Code: ' . curl_errno($ch));
} else {
  echo "Response HTTP Status Code : " . curl_getinfo($ch, CURLINFO_HTTP_CODE);
  echo "\nResponse HTTP Body : " . $resp;
}

// Close request to clear up some resources
curl_close($ch);
```
