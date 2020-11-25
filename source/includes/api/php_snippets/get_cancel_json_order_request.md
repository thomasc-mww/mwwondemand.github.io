```php
<?php

// Get cURL resource
$ch = curl_init();

// Set url
curl_setopt($ch, CURLOPT_URL, 'https://api.mwwondemand.com/api/orders/:id');

// Set method
curl_setopt($ch, CURLOPT_CUSTOMREQUEST, 'PATCH');

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
  "id": <YOUR_VENDOR_PO/ORDER_ID>
  "attributes": {
    "request": "cancel"
    }
  }
}'

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
