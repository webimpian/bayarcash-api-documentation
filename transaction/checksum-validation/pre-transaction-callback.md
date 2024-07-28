# Pre-Transaction Callback

***



Sample code using PHP to validate pre-transaction callback checksum.



```php
<?php
    $secretKey = 'xxxxx';  // Your API secret key obtain from Bayarcash portal
    
    $callbackChecksum = $callbackData['checksum'];
    
    $payloadData = [
        "record_type" => $callbackData['record_type'],
        "exchange_reference_number" => $callbackData['exchange_reference_number'],
        "order_number" => $callbackData['order_number'],
    ];
    
    ksort($payloadData);  // Sort the payload data by key
    $payloadString = implode('|', $payloadData);  // Concatenate values with '|'
    
    $validResponse = hash_hmac('sha256', $payloadString, $secretKey) === $callbackChecksum;  // Validate checksum
```

