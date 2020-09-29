```php
<?php

// Get cURL resource
$ch = curl_init();

// Set url
curl_setopt($ch, CURLOPT_URL, 'https://api.mwwondemand.com/api/webhooks/');

// Set method
curl_setopt($ch, CURLOPT_CUSTOMREQUEST, 'PATCH');

// Set options
curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);

// Set headers
curl_setopt($ch, CURLOPT_HTTPHEADER, [
  "Content-Type: application/vnd.api+json",
  "Authorization: <BEARER_TOKEN>",
  "Accept: application/vnd.api+json; version=1",
 ]
);
// Create body
$body = '{
  \"data\": {
    \"id\": \"\",
    \"type\": \"webhooks\",
    \"attributes\": {
      \"url\": \"http://localhost:3001/mwwondemand-order-notifications\",
      \"printed\": true,
      \"pressed\": true,
      \"cut\": true,
      \"sewn\": true,
      \"turned\": true,
      \"packed\": true
    }
  }
}';

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
